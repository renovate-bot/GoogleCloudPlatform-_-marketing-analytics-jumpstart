# Copyright 2023 Google LLC
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

FROM python:3.10.16-slim

RUN pip install --upgrade pip
RUN pip install poetry

WORKDIR /app
ENV PYTHONPATH=${PYTHONPATH}:${PWD} 

COPY ./pyproject.toml ./README.md /app/
COPY ./ma_components /app/ma_components
RUN poetry config virtualenvs.create false # so that installations is on global python3.10 and not in venv
RUN poetry install