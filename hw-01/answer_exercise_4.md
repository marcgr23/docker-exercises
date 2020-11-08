EXERCISE 4
==========

FROM nginx:1.19.3\
HEALTHCHECK --interval=45s --timeout=5s --start-period=50s --retries=2\
CMD curl --fail http://localhost:80