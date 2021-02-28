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

FROM docker.io/library/ubuntu:xenial
ADD sources.list /etc/apt/sources.list
RUN dpkg --add-architecture armhf && \
    apt-get update && \
    apt-get upgrade -y && \
    apt-get install -y \
            git \ 
            curl \ 
            autoconf \
            gcc-arm-linux-gnueabihf \
            g++-arm-linux-gnueabihf \
            make \
            zip \
            unzip \
            bzip2 \
            file && \
    apt-get remove -y gcc g++ && \
    apt-get autoremove -y && \
    apt-get install -y \
            libx11-dev:armhf \
            libxext-dev:armhf \
            libxrandr-dev:armhf \
            libxrender-dev:armhf \
            libxtst-dev:armhf \
            libxt-dev:armhf \
            libcups2-dev:armhf \
            libfontconfig1-dev:armhf \
            libasound2-dev:armhf \
            libfreetype6-dev:armhf && \ 
    apt-get autoremove -y && \
    apt-get clean all -y


