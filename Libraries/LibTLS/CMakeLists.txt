add_cxx_compile_options(-Wvla)

set(SOURCES
    TLSv12.cpp
)

ladybird_lib(LibTLS tls)
target_link_libraries(LibTLS PRIVATE LibCore LibCrypto LibFileSystem)

find_package(OpenSSL REQUIRED)
target_link_libraries(LibTLS PUBLIC OpenSSL::SSL)
