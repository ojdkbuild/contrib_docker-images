# Copyright 2021, akashche at redhat.com
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
# http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

FROM centos:6
RUN sed -i \
        -e 's/^mirrorlist/#mirrorlist/g' \
        -e 's/^#baseurl=http:\/\/mirror.centos.org\/centos\/$releasever\//baseurl=http:\/\/vault.centos.org\/6.10\//g' \
        /etc/yum.repos.d/CentOS-Base.repo && \
    yum update -y && \
    yum install unzip -y && \
    curl -LO https://github.com/ojdkbuild/praiskup-autotools-epel-6-x86_64/archive/master.zip && \
    unzip ./master.zip && \
    yum install -y \
            ./praiskup-autotools-epel-6-x86_64-master/autotools-latest-1-25.el6.x86_64.rpm \
            ./praiskup-autotools-epel-6-x86_64-master/autotools-latest-autoconf-2.69-11.el6.noarch.rpm \
            ./praiskup-autotools-epel-6-x86_64-master/autotools-latest-automake-1.16.1-4.el6.noarch.rpm \
            ./praiskup-autotools-epel-6-x86_64-master/autotools-latest-libtool-2.4.6-9.el6.x86_64.rpm \
            ./praiskup-autotools-epel-6-x86_64-master/autotools-latest-m4-1.4.18-1.el6.x86_64.rpm \
            ./praiskup-autotools-epel-6-x86_64-master/autotools-latest-runtime-1-25.el6.x86_64.rpm && \
    yum install -y \
            centos-release-scl-rh && \
    yum update -y || true && \
    echo "http://vault.centos.org/6.10/sclo/x86_64/rh" > /var/cache/yum/x86_64/6/centos-sclo-rh/mirrorlist.txt && \
    yum update -y && \
    yum install -y \
            which \
            git \
            zip \
            patch \
            alsa-lib-devel \
            cups-devel \
            freetype-devel \
            libX11-devel \
            libXi-devel \
            libXinerama-devel \
            libXt-devel \
            libXtst-devel \
            libXrandr-devel \
            libXrender-devel \
            xorg-x11-proto-devel \
            elfutils-libelf-devel \
            fontconfig-devel \
            devtoolset-7 \
            autotools-latest && \
    yum clean all && \
    curl -LO https://github.com/ojdkbuild/contrib_jdk10u-ci/releases/download/jdk-10.0.2%2B13/jdk-10.0.2-ojdkbuild-linux-x64.zip && \
    unzip -q jdk-10.0.2-ojdkbuild-linux-x64.zip && \
    mv jdk-10.0.2-ojdkbuild-linux-x64 /bootjdk

