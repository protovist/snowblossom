load("@org_pubref_rules_protobuf//java:rules.bzl", "java_proto_library")

java_binary(
  name = "SnowBlossomNode",
  main_class = "snowblossom.SnowBlossomNode",
  runtime_deps = [
    ":snowblossomlib",
  ]
)
java_binary(
  name = "SnowBlossomMiner",
  main_class = "snowblossom.miner.SnowBlossomMiner",
  runtime_deps = [
    ":minerlib",
  ]
)

java_binary(
  name = "SnowFall",
  main_class = "snowblossom.SnowFall",
  runtime_deps = [
    ":snowblossomlib",
  ]
)
java_binary(
  name = "SnowMerkle",
  main_class = "snowblossom.SnowMerkle",
  runtime_deps = [
    ":snowblossomlib",
  ]
)

java_binary(
  name = "ShowAlgo",
  main_class = "snowblossom.ShowAlgo",
  runtime_deps = [
    ":snowblossomlib",
  ]
)

java_library(
  name = "snowblossomlib",
  srcs = glob(["src/*.java", "src/db/*.java", "src/db/**/*.java"]),
  deps = [
    ":snowblossomprotolib",
    ":trielib",
    "@commons_codec//jar",
    "@commons_math3//jar",
    "@bcprov//jar",
    "@junit_junit//jar",
    "@org_rocksdb_rocksdbjni//jar",
    ],
)

java_library(
  name = "trielib",
  srcs = glob(["src/trie/*.java"]),
  deps = [
    ":snowblossomprotolib",
    "@org_rocksdb_rocksdbjni//jar",
    "@junit_junit//jar",
    "@commons_codec//jar",
  ],
)

java_library(
  name = "minerlib",
  srcs = glob(["src/miner/*.java"]),
  deps = [
    ":snowblossomprotolib",
    ":snowblossomlib",
    "@junit_junit//jar",
    "@commons_codec//jar",
    ":trielib",
    "@bcprov//jar",
  ],
)



java_proto_library(
  name = "snowblossomprotolib",
  protos = glob(["proto/*.proto"]),
  with_grpc = True,
  verbose = 1,
)

java_test(
    name = "trie_test",
    srcs = ["test/trie/TrieTest.java"],
    test_class = "snowblossom.trie.TrieTest",
    size="small",
    deps = [
      "@junit_junit//jar",
      ":snowblossomlib",
      ":trielib",
      "@org_pubref_rules_protobuf//java:grpc_compiletime_deps",
    ],
)
java_test(
    name = "trie_rocks_test",
    srcs = ["test/trie/TrieRocksTest.java"],
    test_class = "snowblossom.trie.TrieRocksTest",
    size="small",
    deps = [
      "@junit_junit//jar",
      ":snowblossomlib",
      ":trielib",
      "@org_pubref_rules_protobuf//java:grpc_compiletime_deps",
      "@commons_io//jar",
    ],
)

java_test(
  name = "prng_stream_test",
  srcs = ["test/PRNGStreamTest.java"],
  test_class = "snowblossom.PRNGStreamTest",
  size="small",
  deps = [
      "@junit_junit//jar",
      ":snowblossomlib",
      "@org_pubref_rules_protobuf//java:grpc_compiletime_deps",
      "@commons_codec//jar",
  ],
)

java_test(
  name = "block_ingestor_test",
  srcs = ["test/BlockIngestorTest.java"],
  test_class = "snowblossom.BlockIngestorTest",
  size="small",
  deps = [
      "@junit_junit//jar",
      ":snowblossomlib",
      "@commons_codec//jar",
      "//:snowblossomprotolib",
  ],
)

java_test(
  name = "pow_util_test",
  srcs = ["test/PowUtilTest.java"],
  test_class = "snowblossom.PowUtilTest",
  size="small",
  deps = [
      "@junit_junit//jar",
      ":snowblossomlib",
      "@commons_codec//jar",
      "//:snowblossomprotolib",
  ],
)
java_test(
  name = "address_util_test",
  srcs = ["test/AddressUtilTest.java"],
  test_class = "snowblossom.AddressUtilTest",
  size="small",
  deps = [
      "@junit_junit//jar",
      ":snowblossomlib",
      "@commons_codec//jar",
      "//:snowblossomprotolib",
  ],
)
java_test(
  name = "digest_util_test",
  srcs = ["test/DigestUtilTest.java"],
  test_class = "snowblossom.DigestUtilTest",
  size="small",
  deps = [
      "@junit_junit//jar",
      ":snowblossomlib",
      "@commons_codec//jar",
      "//:snowblossomprotolib",
  ],
)



java_test(
  name = "signature_test",
  srcs = ["test/SignatureTest.java"],
  test_class = "snowblossom.SignatureTest",
  size="small",
  deps = [
      "@junit_junit//jar",
      ":snowblossomlib",
      "@commons_codec//jar",
      "@bcprov//jar",
  ],
)

java_test(
  name = "validation_test",
  srcs = ["test/ValidationTest.java"],
  test_class = "snowblossom.ValidationTest",
  size="small",
  deps = [
      "@junit_junit//jar",
      ":snowblossomlib",
      "@commons_codec//jar",
      "@org_pubref_rules_protobuf//java:grpc_compiletime_deps",
      "//:snowblossomprotolib",
  ],
)



java_test(
  name = "snow_fall_merkle_test",
  srcs = ["test/SnowFallMerkleTest.java"],
  test_class = "snowblossom.SnowFallMerkleTest",
  size="medium",
  deps = [
      "@junit_junit//jar",
      ":snowblossomlib",
      "@org_pubref_rules_protobuf//java:grpc_compiletime_deps",
      "@commons_codec//jar",
  ],
)

java_test(
  name = "snow_merkle_proof_test",
  srcs = ["test/SnowMerkleProofTest.java"],
  test_class = "snowblossom.SnowMerkleProofTest",
  size="medium",
  deps = [
      "@junit_junit//jar",
      ":snowblossomlib",
      ":snowblossomprotolib",
      "@org_pubref_rules_protobuf//java:grpc_compiletime_deps",
      "@commons_codec//jar",
  ],
)



