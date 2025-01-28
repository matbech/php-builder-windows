# PHP Builder for Windows

<a href="https://github.com/matbech/php-builder-windows" title="PHP Builder Windows"><img alt="Build status" src="https://github.com/matbech/php-builder-windows/workflows/Build%20PHP%20master/badge.svg"></a>
<a href="https://github.com/matbech/php-builder-windows/blob/main/LICENSE" title="license"><img alt="LICENSE" src="https://img.shields.io/badge/license-MIT-428f7e.svg"></a>
<a href="https://github.com/matbech/php-builder-windows#Builds" title="builds"><img alt="PHP Versions Supported" src="https://img.shields.io/badge/php-%3E%3D%208.0-8892BF.svg"></a>

> Build PHP snapshots for Windows.

## Builds

The following configurations are built nightly.

- `nts-x64`, `nts-x64-AVX`, `nts-x64-AVX2`, `nts-x64-AVX512`.
- `debug-pack`, `devel=pack` for each configuration.
- `test pack` for the version.

### PHP 8.5.0-dev/master
[https://github.com/matbech/php-builder-windows/releases/tag/php8.5](https://github.com/shivammathur/php-builder-windows/releases/tag/php8.5)

### PHP 8.4.x-dev
[https://github.com/matbech/php-builder-windows/releases/tag/php8.4](https://github.com/shivammathur/php-builder-windows/releases/tag/php8.4)

## Install

To install a PHP snapshot, open an elevated PowerShell session and run these commands. You can change the configure variables as per your requirements.

```ps1
# Configure
$php_dir = 'C:\tools\php' # Set this as per your setup
$arch    = 'x64'          # Set x64
$ts      = $False         # Set $False for nts or $True for ts
$version = '8.4'          # Set 8.4, or 8.5

# Install
New-Item -Path $php_dir -Type Directory -Force
Invoke-WebRequest -UseBasicParsing -Uri https://github.com/matbech/php-builder-windows/releases/latest/download/Get-Php.ps1 -OutFile $php_dir\Get-Php.ps1
. $php_dir\Get-Php.ps1 -Architecture $arch -ThreadSafe $ts -Path $php_dir -Version $version

# Test
. $php_dir\php -v
```

## License

The code in this project is licensed under the [MIT license](http://choosealicense.com/licenses/mit/).
Please see the [license file](LICENSE) for more information. This project has multiple [dependencies](#dependencies "Dependencies for this project"). Their licenses can be found in their respective repositories.

## Dependencies

- [php/php-src](https://github.com/php/php-src)
- [php/web-rmtools](https://github.com/php/web-rmtools)
- [php/php-sdk-binary-tools](https://github.com/php/php-sdk-binary-tools)
- [Oracle instantclient](https://www.oracle.com/downloads/licenses/instant-client-lic.html)
