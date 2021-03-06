cet_test( LArPropertiesStandard_test
  LIBRARIES
  lardataalg_DetectorInfo
  cetlib
  DATAFILES lartest_standard.fcl
  TEST_ARGS ./lartest_standard.fcl
  INSTALL_BIN
  INSTALL_SOURCE
)

cet_test( LArPropertiesLArTPCdetector_test
  HANDBUILT
  DATAFILES lartest_lartpcdetector.fcl
  TEST_EXEC LArPropertiesStandard_test
  TEST_ARGS ./lartest_lartpcdetector.fcl
)

cet_test( LArPropertiesBo_test
  HANDBUILT
  DATAFILES lartest_bo.fcl
  TEST_EXEC LArPropertiesStandard_test
  TEST_ARGS ./lartest_bo.fcl
)


cet_test( DetectorClocksStandard_test
  LIBRARIES
  lardataalg_DetectorInfo
  cetlib
  DATAFILES clockstest_standard.fcl
  TEST_ARGS ./clockstest_standard.fcl
  INSTALL_BIN
  INSTALL_SOURCE
)

cet_test( DetectorTimingTypes_test USE_BOOST_UNIT)

cet_test( DetectorTimingsStandard_test
  LIBRARIES
  lardataalg_DetectorInfo
  cetlib
  DATAFILES clockstest_standard.fcl
  TEST_ARGS ./clockstest_standard.fcl
  INSTALL_BIN
  INSTALL_SOURCE
)

cet_test( DetectorClocksLArTPCdetector_test
  HANDBUILT
  DATAFILES clockstest_lartpcdetector.fcl
  TEST_EXEC DetectorClocksStandard_test
  TEST_ARGS ./clockstest_lartpcdetector.fcl
)

cet_test( DetectorClocksBo_test
  HANDBUILT
  DATAFILES clockstest_bo.fcl
  TEST_EXEC DetectorClocksStandard_test
  TEST_ARGS ./clockstest_bo.fcl
)

cet_test( DetectorClocksCSU40L_test
  HANDBUILT
  DATAFILES clockstest_csu40l.fcl
  TEST_EXEC DetectorClocksStandard_test
  TEST_ARGS ./clockstest_csu40l.fcl
)

cet_make_exec( DetectorPropertiesStandard_test
  LIBRARIES
  lardataalg_DetectorInfo
  cetlib
)

cet_test( DetectorPropertiesLArTPCdetector_test
  HANDBUILT
  DATAFILES dettest_lartpcdetector.fcl
  TEST_EXEC DetectorPropertiesStandard_test
  TEST_ARGS ./dettest_lartpcdetector.fcl
)

# this test requires larcore/Geometry/geometry_bo.fcl
##cet_test( DetectorPropertiesBo_test
##  HANDBUILT
##  DATAFILES dettest_bo.fcl
##  TEST_EXEC DetectorPropertiesStandard_test
##  TEST_ARGS ./dettest_bo.fcl
##)

install_source()
install_fhicl()
