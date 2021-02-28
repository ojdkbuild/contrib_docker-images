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
    yum install -y \
            which \
            git \
            zip \
            unzip \
            java-1.7.0-openjdk-devel \
            autoconf \
            automake \
            alsa-lib-devel \
            binutils \
            cups-devel \
            desktop-file-utils \
            elfutils \
            fontconfig-devel \
            freetype-devel \
            gcc-c++ \
            libX11-devel \
            libXi-devel \
            libXinerama-devel \
            libXt-devel \
            libXtst-devel \
            libXrender-devel \
            xorg-x11-proto-devel \
            dejavu-serif-fonts \
            dejavu-sans-fonts \
            dejavu-sans-mono-fonts && \
    yum clean all

