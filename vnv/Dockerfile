ARG FROM_IMAGE=vnv_base
FROM ${FROM_IMAGE}

#Install the simple application example. 
COPY . ${SOURCE_DIR}/issues  
RUN  cd ${SOURCE_DIR}/issues \
     && mkdir build \
     && cd build \
     && cmake -DInjection_DIR=${VNV_DIR}/lib/cmake -DCMAKE_INSTALL_PREFIX=${SOFTWARE_DIR}/plugins/issues .. \
     && make \
     && make install  \
     && cp -r ../vnv/config ${SOFTWARE_DIR}/plugins/issues/gui \
     && rm -r ${SOURCE_DIR}/issues

RUN ${VNV_REGISTER} gui ISSUES ${SOFTWARE_DIR}/plugins/issues/gui/vnv.__registration__
RUN ${VNV_REGISTER} plugin ISSUES ${SOFTWARE_DIR}/plugins/issues/lib/libissues.so


