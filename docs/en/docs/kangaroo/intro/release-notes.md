---
MTPE: windsonsea
date: 2024-06-03
---

# Container Registry Release Notes

This page lists the release notes of the container registry, so that you can
understand the evolution path and feature changes of each version.

*[Kangaroo]: Internal dev codename for the container registry
*[Kpanda]: Internal dev codename for container management
*[Harbor]: An open-source container registry tool and a CNCF graduated project

## 2024-11-30

### v0.24.0

- **Fixed** an issue where creating a managed Harbor instance failed when different clusters used the same MinIO name.

## 2024-10-31

### v0.23.0

- **Added** validation prompts to prevent image pushes when image proxy is enabled in Harbor repositories.
- **Added** support for custom image namespaces in Docker Registry.
- **Added** support for deleting middleware when deleting Harbor instances.
- **Fixed** a delay issue in the count when creating image namespaces.
- **Fixed** an issue where managed Harbor ChartMuseum did not correctly use Redis.
- **Fixed** inconsistent return values between the `GetRepository` and `ListRepository` APIs.
- **Fixed** a 405 error prompt when deleting an admin-integrated docker-registry image.
- **Fixed** image vulnerability issues.
- **Fixed** an issue where creating a Harbor MinIO instance would cause unexpected restarts.

## 2024-09-30

### v0.22.0

- **Added** validation to allow only one instance of MinIO to be created within a namespace.
- **Added** hints for available image space when pushing images.
- **Improved** the conflict to use an already used middleware when creating a managed Harbor.
- **Fixed** the issue where a repository with a name consisting solely of digits could not be deleted in integrated or managed image repositories.
- **Added** support for quickly creating managed Harbor through a one-click creation of Redis/MinIO/PostgreSQL.
- **Improved** the validation of middleware instances when creating managed Harbor, disallowing reuse.

## 2024-08-30

### v0.21.1

- **Added** a feature of quickly creating managed Harbor instances through a one-click setup for Redis/Minio/PostgreSQL.
- **Improved** the validation of middleware instances when creating managed Harbor, to reuse is disabled now.
- **Improved** the adaptability to middlewares, so that a middleware created through the container registry can also
  be managed by the DCE 5.0 middleware (`mcamel`) module.
- **Added** cluster status validation when creating managed Harbor; Harbor can only be created in running clusters.
- **Fixed** the issue of missing audit logs when editing or deleting managed Harbor.
- **Fixed** the error when pulling images through the built-in middleware interface.
- **Fixed** the issue where the Admin could not operate Harbor via the API after enabling OIDC.

## 2024-07-31

### v0.20.0

- **Fixed** an issue where online Harbor creation failed due to some images failing to be pulled
- **Fixed** inconsistency in the number of permission between the Admin user and custom roles
- **Fixed** some permission overflow issues

## 2024-06-30

### v0.19.0

- **Fixed** an issue that prevented the deletion of a workspace, incorrectly prompting users to unbind a registry space that had no actual binding relationship with the workspace.

## 2024-05-31

### v0.18.1

- **Improved** the accuracy of login command prompts after integrating Harbor administrator into the container registry
- **Fixed** pagination issue in the image selector interface on the application workbench

## 2024-04-30

### v0.17.0

- **Improved** deletion prompts for Docker/Jfrog registry
- **Improved** image download counts
- **Improved** the registry space list view for Docker/Jfrog registry from the administrator's perspective

## 2024-03-29

### v0.16.1

- **Added** best practice documentation for deploying Harbor via LoadBalancer mode
- **Added** support for upgrading Kangaroo through Kpanda Helm application updates
- **Fixed** an issue with failed image deletion in Docker Registry
- **Fixed** an issue with failed creation of image recycling rules for regular tenants (with wsadmin permissions)
- **Fixed** dependency issue in creating and deleting Harbor with custom role management
- **Fixed** an error occurred when creating a container registry with Chinese characters in the description

## 2024-01-31

### v0.15.0

- **Fixed** an error when querying registry space for associated JFrog container registry
- **Fixed** a failure to generate login command

## 2023-12-29

### v0.14.0

- **Improved** compatibility for supporting illegal k8s usernames
- **Fixed** an issue with consuming excessive bandwidth during large-scale image synchronization
- **Fixed** an issue with high latency in querying large-scale images in a single registry space

## 2023-11-30

### v0.13.1

- **Fixed** an issue with binding workspace to registry space
- **Fixed** an issue with granting authorization to all public registry spaces when generating login instructions

## 2023-10-31

### v0.12.0

- **Added** support for quick deployment of middleware when creating a managed Harbor in non-platinum versions
- **Added** best practices for publishing Harbor Nginx configuration
- **Added** best practices for resource planning when releasing container registries
- **Improved** resource validation when creating a managed Harbor
- **Improved** prompt for installing cert manager as a dependency for Harbor operator

## 2023-09-06

### v0.11.0

- **Added** harbor hosting status verification
- **Added** deployment to download station
- **Added** best practices for Nginx proxy, resource capacity planning
- **Fixed** an issue preventing updates to managed Harbor description
- **Improved** display of truncated registry space in bootstrap container registry
- **Improved** a frontend error for WS admin when creating recycle rules

## 2023-08-02

### v0.10.0

- **Added** a solution for migrating/backing up/restoring container registry,
  which has been verified through the migration of the release-ci repository
- **Added** best practices for logging into non-secure container registry
- **Added** support for using the internal middleware MINIO when creating managed Harbor
- **Added** support for the PG mode of Renmin Jincang
- **Improved** the format validation for PG and Redis addresses when creating managed Harbor
- **Improved** grayed-out and prompt optimization for unauthorized access
- **Improved** handling of special cases after unbinding clusters

## 2023-07-02

### v0.9.0

- **Added** support for selecting the middleware `minio` instance when creating managed harbor
- **Added** support for key auditing functionality in `Ghippo`
- **Improved** validation for container registry resources under a workspace (WS) when deleting the workspace
- **Improved** state info of managed harbor after unbinding clusters
- **Fixed** an issue where `Ghippo workspace` resources could not be unbound
- **Fixed** an issue with `Sidecar` injection
- **Fixed** an issue where images could not be pushed when selecting `minio` during harbor creation

## 2023-06-05

### v0.8.0

#### New Features

- **Added** image description information to the harbor type repository
- **Added** instance status to the registry space list
- **Added** support for randomly generating `nodeport` port numbers when creating a harbor
- **Added** validation for duplicate usage of `redis`, `postgresql`, and `s3` in the creation of harbor
- **Added** image recycling feature to the `project`

#### Fixes

- **Fixed** the concatenation error in the offline deployment of managed harbor image addresses
- **Fixed** pagination issue in the docker registry type `project` list
- **Fixed** search issue in the docker registry type `repository`
- **Fixed** existing account issue when creating robot accounts

#### Improvements

- **Added** job cleanup logic
- **Removed** the `project` field from the interface for obtaining temporary login instructions
- **Improved** login instructions
- **Improved** logic for image scanning judgment

## 2023-05-08

### v0.7.0

- **Added** support page configuration image synchronization between multiple instances
- **Added** support for associating `jfrog` registry in workspaces
- **Added** support for creating managed harbor in offline `ARM` environment
- **Fixed** an issue that the registry integration URL could not be updated after modification
- **Fixed** logical incompatibilities after `Project` was deleted from the native harbor page
- **Improved** the performance of docking `jfrog` interface to within `2s`

## 2023-04-07

### v0.6.2

- **Added** support custom roles in global management, granting different role permissions to users
- **Added** support for generating temporary login commands
- **Added** managed harbor to support `cpu, memory` verification
- **Added** managed harbor support for editing image scanners
- **Added** managed harbor support for using `S3` storage
- **Fixed** an issue that the installation byte of harbor-operator helm is too large
- **Improved** the performance of the image list feature page, and propose a separate `Project` list page

## 2023-03-15

### v0.5.0

- **Added** support for creating managed Harbor instances with `NodePort` exposure and validation of port availability.
- **Added** support for creating managed Harbor instances with `https` exposure.
- **Added** support for creating managed Harbor instances with `DCE 5.0 ODIC` integration, allowing users to log in to Harbor using `DCE 5.0` credentials.
- **Added** support for validating the installation of `harbor-operator` in the deployed cluster when creating managed Harbor instances.
- **Added** support for deploying `redis` instances using the middleware module in managed Harbor instances.
- **Added** support for modifying `Admin` password, resource quotas, `Redis` instances, and access types in managed Harbor instances.
- **Added** support for automatically creating image scanners in managed Harbor instances.
- **Added** support for repository integration, including validation of user passwords and permissions.
    - **Added** support for validating the correctness of username and password in repository integration and ensuring that the user has administrator privileges.
    - **Added** support for validating the correctness of username and password in repository integration.
- **Added** support for fuzzy searching in the repository integration list.
- **Added** support for editing the visibility of projects as public or private.
- **Added** support for displaying multi-architecture images in the pages of Harbor and Docker Registry repositories.
- **Fixed** support for accessing Harbor and Docker Registry repositories via `https` integration.

## 2022-12-30

### v0.4.0

- **Added** support for creating managed registries based on Harbor
- **Added** support multi-copy deployment
- **Added** support lifecycle management of container registry
- **Added** support deploying managed harbor instances in any namespace under any cluster of the platform
- **Added** support platform access and management of external Harbor, Docker Registry container registry
- **Added** support separate allocation of private registry space for platform workspace (tenant)
- **Added** support for creating public/private registry spaces
- **Added** support workspace (tenant) independent access to external Harbor, Docker Registry container registry
- **Added** support for selecting images through the image selector when deploying applications
- **Added** support image scanning
