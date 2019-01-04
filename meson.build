project('xtl', 'cpp', version:'0.5.2', license:'BSD-3-Clause', default_options : ['warning_level=3', 'cpp_std=c++14'])

xtl_dep = declare_dependency(include_directories:include_directories('include'))

install_headers([
 'include/xtl/xany.hpp',
 'include/xtl/xoptional.hpp',
 'include/xtl/xmeta_utils.hpp',
 'include/xtl/xproxy_wrapper.hpp',
 'include/xtl/xtype_traits.hpp',
 'include/xtl/xbase64.hpp',
 'include/xtl/xclosure.hpp',
 'include/xtl/xcomplex_sequence.hpp',
 'include/xtl/xspan.hpp',
 'include/xtl/xoptional_sequence.hpp',
 'include/xtl/xdynamic_bitset.hpp',
 'include/xtl/xsequence.hpp',
 'include/xtl/xjson.hpp',
 'include/xtl/xvariant.hpp',
 'include/xtl/xfunctional.hpp',
 'include/xtl/xspan_impl.hpp',
 'include/xtl/xbasic_fixed_string.hpp',
 'include/xtl/xvariant_impl.hpp',
 'include/xtl/xhash.hpp',
 'include/xtl/xcomplex.hpp',
 'include/xtl/xtl_config.hpp',
 'include/xtl/xiterator_base.hpp',
 'include/xtl/xhierarchy_generator.hpp'
 ]
,
 subdir:'xtl'
)


pkgc = import('pkgconfig')
pkgc.generate(name: 'xtl',
    version: meson.project_version(),
    description: 'The x template library '
)


tests_sources = [
 'test/test_xbase64.cpp',
 'test/test_xbasic_fixed_string.cpp',
 'test/test_xclosure.cpp',
 'test/test_xcomplex.cpp',
 'test/test_xcomplex_sequence.cpp',
 'test/test_xdynamic_bitset.cpp',
 'test/test_xhash.cpp',
 'test/test_xhierarchy_generator.cpp',
 'test/test_xiterator_base.cpp',
 'test/test_xmeta_utils.cpp',
 'test/test_xoptional.cpp',
 'test/test_xproxy_wrapper.cpp',
 'test/test_xsequence.cpp',
 'test/test_xtype_traits.cpp',
 'test/test_xvariant.cpp'
 ]

if get_option('BUILD_TESTS')
  gtest_dep = dependency('gtest', main : true, fallback : ['gtest', 'gtest_main_dep'])
  test_exe = executable('xtl-test', tests_sources, dependencies:[xtl_dep, gtest_dep])
  test('xtl-test', test_exe)
endif
