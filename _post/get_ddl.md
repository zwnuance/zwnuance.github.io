###获取对象DDL语句
例如：
dbms_metadata.get_ddl('TABLE', 'TABLENAME', 'SCHEMA')

-- GET_DDL:     Return the metadata for a single object as DDL.
--      This interface is meant for casual browsing (e.g., from SQLPlus)
--      vs. the programmatic OPEN / FETCH / CLOSE interfaces above.
-- PARAMETERS:
--      object_type     - The type of object to be retrieved.
--      name            - Name of the object.
--      schema          - Schema containing the object.  Defaults to
--                        the caller's schema.
--      version         - The version of the objects' metadata.
--      model           - The object model for the metadata.
--      transform       - XSL-T transform to be applied.
-- RETURNS:     Metadata for the object transformed to DDL as a CLOB.

  FUNCTION get_ddl (
                object_type     IN  VARCHAR2,
                name            IN  VARCHAR2,
                schema          IN  VARCHAR2 DEFAULT NULL,
                version         IN  VARCHAR2 DEFAULT 'COMPATIBLE',
                model           IN  VARCHAR2 DEFAULT 'ORACLE',
                transform       IN  VARCHAR2 DEFAULT 'DDL')
        RETURN CLOB;

返回clob类型的数据，无法直接查看。
通过调用dbms_lob.substr函数将clob转换成可查看的字符串。
例如:
select dbms_lob.substr(
    dbms_metadata.get_ddl('TABLE', 'TABLE_NAME', 'SCHEMA')
) from dual;