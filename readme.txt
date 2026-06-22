# AGNMLCC

AGNMLCC stands for AGN Microlensing Candidate Catalog.

This catalog contains 304 isolated, single-peaked, approximately symmetric,
PSPL-like AGN flare candidates selected from ZTF AGN light curves. These
sources are microlensing candidates, not confirmed microlensing events.

The catalog products are:

  AGNMLCC.csv
  AGNMLCC_QZO_auxiliary_catalog.csv

AGNMLCC.csv contains the main candidate sample used for the catalog-level
statistics, event-rate estimates, and selection-corrected optical-depth
estimates. The objects in this main catalog have relatively secure AGN/QSO
identifications based on external catalog information. In contrast,
AGNMLCC_QZO_auxiliary_catalog.csv contains source-only QZO candidates, whose
source nature is less secure because they are selected only from the QZO
machine-learning quasar-candidate catalog and are not independently matched to
other AGN catalogs. This auxiliary sample may therefore include stellar-source
microlensing contaminants and is not included in the main statistical
estimates.

For the QZO auxiliary catalog, no additional matching was performed against
the selected external comparison samples of He et al. and Ren et al., or
against the LAMOST and SDSS DR16Q-based physical-property catalogs. Therefore,
external_match is set to "-", and all external spectroscopic physical-property
columns are left blank for this auxiliary sample.


-----------------------------------------------------------------------
Catalog Summary
-----------------------------------------------------------------------

Total main candidates: 304

Confidence classes:
  HIGH : 66
  MED  : 125
  LOW  : 113

Redshift information:
  Spectroscopic redshift : 203
  Photometric redshift   : 94
  Unknown redshift       : 7

Auxiliary QZO-only catalog:
  Total auxiliary candidates : 77
  HIGH                       : 45
  MED                        : 20
  LOW                        : 12

External-match flags:
  H   : matched to the AGN flare sample of He et al.
  R   : matched to the EVQ sample of Ren et al.
  H;R : matched to both selected external comparison samples
  -   : no match to these selected external comparison samples

Compact catalog-level physical-property columns are provided when reliable
external catalog measurements are available. These include LAMOST single-epoch
black-hole mass and continuum-luminosity measurements, as well as SDSS
DR16Q-based quasar physical quantities.

Cross-matching the 304 main candidates within 3 arcsec yields:
  Clean LAMOST physical-property measurements      : 33
  Clean SDSS DR16Q-based physical-property values  : 125
  Covered by both LAMOST and SDSS DR16Q-based sets : 22
  Covered by at least one physical-property set    : 136

-----------------------------------------------------------------------
Missing-value Convention
-----------------------------------------------------------------------

Blank entries in numerical columns indicate unavailable or non-clean
measurements.

Blank entries in external physical-property columns indicate unavailable,
unmatched, or non-clean measurements.

Missing categorical entries are marked as unknown when appropriate.

The value "-" in external_match means no match to the selected external
comparison samples.

-----------------------------------------------------------------------
WFST_ID Format
-----------------------------------------------------------------------

Each source is assigned a unique WFST_ID that encodes its sky position in
decimal degrees.

The format is:

  WFST_{RA}{+/-}{Dec}

where RA and Dec are recorded to six decimal places after removing the
decimal point.

For example:

  WFST_016487653+34352818

corresponds to:

  RA  = 16.487653 deg
  Dec = +34.352818 deg

Explicit ra and dec columns are also provided in decimal degrees.

-----------------------------------------------------------------------
Catalog Fields
-----------------------------------------------------------------------

Column Name                 Unit        Description
-----------------------------------------------------------------------------------------------
WFST_ID                     --          Unique source identifier encoding the sky position.
ra                          deg         Right ascension in decimal degrees.
dec                         deg         Declination in decimal degrees.
z                           --          Redshift. Blank if unavailable.
z_err                       --          Redshift uncertainty when provided by the source catalog.
z_type                      --          Redshift type: spec, phot, or unknown.
confidence                  --          Candidate confidence class: high, med, or low.

t0_mcmc                     MJD         Best-fit peak time from the MCMC PSPL-like fit.
t0_err                      day         Posterior uncertainty of t0_mcmc, written as +upper/-lower.
tE_mcmc                     day         Best-fit observer-frame Einstein timescale from the MCMC PSPL-like fit.
tE_err                      day         Posterior uncertainty of tE_mcmc, written as +upper/-lower.
u0_mcmc                     --          Best-fit impact parameter from the MCMC PSPL-like fit.
u0_err                      --          Posterior uncertainty of u0_mcmc, written as +upper/-lower.
A_max                       --          Peak magnification of the fitted PSPL-like model.

g_s                         mag         Fitted source-component magnitude in the ZTF g band.
g_base                      mag         Fitted baseline magnitude in the ZTF g band.
r_s                         mag         Fitted source-component magnitude in the ZTF r band.
r_base                      mag         Fitted baseline magnitude in the ZTF r band.
i_s                         mag         Fitted source-component magnitude in the ZTF i band.
i_base                      mag         Fitted baseline magnitude in the ZTF i band.

chi2                        --          Total chi-square of the PSPL-like fit.
dof                         --          Degrees of freedom of the fit.
chi2/dof                    --          Reduced chi-square of the fit.

source                      --          Input catalog provenance. Multiple catalogs are separated by commas.
type                        --          Original source type code from Milliquas when available; unknown if unavailable.
external_match              --          Compact external-match flag: H, R, H;R, or -.

logMBH_lamost               dex         LAMOST single-epoch black-hole mass, log10(M_BH/M_sun).
logMBH_method_lamost        --          Broad emission line used for the LAMOST mass estimate: MgII, Hbeta, or CIV.
logL_lamost                 dex         LAMOST continuum luminosity, log10(lambda L_lambda / erg s^-1).
logL_wave_lamost            Angstrom    Rest-frame wavelength of the LAMOST continuum luminosity.
broad_fwhm_lamost           km/s        Broad-line FWHM corresponding to logMBH_method_lamost.
broad_ew_lamost             Angstrom    Broad-line equivalent width corresponding to logMBH_method_lamost.

logMBH_SDSSDR16Q            dex         SDSS DR16Q-based single-epoch black-hole mass, log10(M_BH/M_sun).
logMBH_method_SDSSDR16Q     --          Broad emission line used for the SDSS DR16Q-based mass estimate: MgII, Hbeta, or CIV.
logL_SDSSDR16Q              dex         SDSS DR16Q-based continuum luminosity, log10(lambda L_lambda / erg s^-1).
logL_wave_SDSSDR16Q         Angstrom    Rest-frame wavelength of the SDSS DR16Q-based continuum luminosity.
broad_fwhm_SDSSDR16Q        km/s        Broad-line FWHM corresponding to logMBH_method_SDSSDR16Q.
broad_ew_SDSSDR16Q          Angstrom    Broad-line equivalent width corresponding to logMBH_method_SDSSDR16Q.

-----------------------------------------------------------------------------------------------







