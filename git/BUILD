package(default_visibility = ["//visibility:public"])

load("@io_bazel_rules_docker//container:container.bzl", "container_image")
load("@package_bundle//file:packages.bzl", "packages")

DISTRO_PACKAGES = {
    "_debian9": packages,
}

# An image for git
[[container_image(
    name = ("git" if (not mode) else mode[1:]) + distro_suffix,
    base = "//base" + (mode if mode else ":base") + distro_suffix,
    debs = [
        DISTRO_PACKAGES[distro_suffix]["git"],
        DISTRO_PACKAGES[distro_suffix]["libpcre3"],
        DISTRO_PACKAGES[distro_suffix]["zlib1g"],
        DISTRO_PACKAGES[distro_suffix]["libpthread-stubs0-dev"],
        DISTRO_PACKAGES[distro_suffix]["git-man"],
        DISTRO_PACKAGES[distro_suffix]["krb5-locales"],
        DISTRO_PACKAGES[distro_suffix]["less"],
        DISTRO_PACKAGES[distro_suffix]["libbsd0"],
        DISTRO_PACKAGES[distro_suffix]["libcurl3-gnutls"],
        DISTRO_PACKAGES[distro_suffix]["libedit2"],
        DISTRO_PACKAGES[distro_suffix]["liberror-perl"],
        DISTRO_PACKAGES[distro_suffix]["libexpat1"],
        DISTRO_PACKAGES[distro_suffix]["libffi6"],
        DISTRO_PACKAGES[distro_suffix]["libgdbm3"],
        DISTRO_PACKAGES[distro_suffix]["libgmp10"],
        DISTRO_PACKAGES[distro_suffix]["libgnutls30"],
        DISTRO_PACKAGES[distro_suffix]["libgpm2"],
        DISTRO_PACKAGES[distro_suffix]["libgssapi-krb5-2"],
        DISTRO_PACKAGES[distro_suffix]["libhogweed4"],
        DISTRO_PACKAGES[distro_suffix]["libidn2-0"],
        DISTRO_PACKAGES[distro_suffix]["libk5crypto3"],
        DISTRO_PACKAGES[distro_suffix]["libkeyutils1"],
        DISTRO_PACKAGES[distro_suffix]["libkrb5-3"],
        DISTRO_PACKAGES[distro_suffix]["libkrb5support0"],
        DISTRO_PACKAGES[distro_suffix]["libldap-2.4-2"],
        DISTRO_PACKAGES[distro_suffix]["libldap-common"],
        DISTRO_PACKAGES[distro_suffix]["libncurses5"],
        DISTRO_PACKAGES[distro_suffix]["libnghttp2-14"],
        DISTRO_PACKAGES[distro_suffix]["libp11-kit0"],
        DISTRO_PACKAGES[distro_suffix]["libperl5.24"],
        DISTRO_PACKAGES[distro_suffix]["libpopt0"],
        DISTRO_PACKAGES[distro_suffix]["libpsl5"],
        DISTRO_PACKAGES[distro_suffix]["librtmp1"],
        DISTRO_PACKAGES[distro_suffix]["libsasl2-2"],
        DISTRO_PACKAGES[distro_suffix]["libsasl2-modules"],
        DISTRO_PACKAGES[distro_suffix]["libsasl2-modules-db"],
        DISTRO_PACKAGES[distro_suffix]["libssh2-1"],
        DISTRO_PACKAGES[distro_suffix]["libssl1.0.2"],
        DISTRO_PACKAGES[distro_suffix]["libssl1.1"],
        DISTRO_PACKAGES[distro_suffix]["libtasn1-6"],
        DISTRO_PACKAGES[distro_suffix]["libunistring0"],
        DISTRO_PACKAGES[distro_suffix]["libx11-6"],
        DISTRO_PACKAGES[distro_suffix]["libx11-data"],
        DISTRO_PACKAGES[distro_suffix]["libxau6"],
        DISTRO_PACKAGES[distro_suffix]["libxcb1"],
        DISTRO_PACKAGES[distro_suffix]["libxdmcp6"],
        DISTRO_PACKAGES[distro_suffix]["libxext6"],
        DISTRO_PACKAGES[distro_suffix]["libxmuu1"],
        DISTRO_PACKAGES[distro_suffix]["netbase"],
        DISTRO_PACKAGES[distro_suffix]["openssh-client"],
        DISTRO_PACKAGES[distro_suffix]["openssl"],
        DISTRO_PACKAGES[distro_suffix]["patch"],
        DISTRO_PACKAGES[distro_suffix]["perl"],
        DISTRO_PACKAGES[distro_suffix]["perl-modules-5.24"],
        DISTRO_PACKAGES[distro_suffix]["publicsuffix"],
        DISTRO_PACKAGES[distro_suffix]["rename"],
        DISTRO_PACKAGES[distro_suffix]["rsync"],
        DISTRO_PACKAGES[distro_suffix]["xauth"],
    ],
) for mode in [
    "",
    ":debug",
]] for distro_suffix in ["_debian9"]]

# Provide aliases so the default images use debian9
alias(
    name = "git",
    actual = ":git_debian9",
)

alias(
    name = "debug",
    actual = ":debug_debian9",
)
