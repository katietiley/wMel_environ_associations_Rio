Supporting the manuscript:  
# Climate and landscape features associated with successful Wolbachia replacement in the municipality of Rio de Janeiro, Brazil  
Authors: Katie Tiley, Katie Milligan Susong, Steffen Knoblauch, Kathleen M O’Reilly, and Oliver Brady

  
#### Abstract:  
  
**Background**  
  
Wolbachia replacement is a promising strategy for reducing arboviral transmission by Aedes aegypti. Wolbachia-infection is refractory to arboviruses, including dengue and chikungunya, and Wolbachia spreads in mosquito populations by maternal transmission and cytoplasmic incompatibility, whereby mating between infected males and uninfected females produce non-viable offspring. Deployment programmes seek to establish stable, high Wolbachia prevalence through the release of Wolbachia-infected mosquitoes, however, prevalence varies spatially, particularly in complex urban environments where fine-scale heterogeneity in temperature and built environment may influence mosquito population dynamics. Here, we investigate how climate and landscape features are associated with heterogeneous Wolbachia replacement outcomes using wMel prevalence data from releases in the municipality of Rio de Janeiro, Brazil (2017–2019).  
  
**Methods**  
  
Across a 26-month period, 500 x 500 m spatial units were clustered into four distinct replacement trajectories: unsuccessful, low, moderate, and high success, defined using predicted Wolbachia prevalence time series generated from cell-level binomial regression models and grouped using k-means clustering. Associations were explored between each trajectory and features related to Ae. aegypti habitat suitability, climate sensitivity, flight barriers, and Wolbachia deployment barriers using a multinomial generalised additive model (GAM). We used forward selection based on Akaike Information Criterion, explicit consideration of spatial autocorrelation and screened for collinearity among covariates. Of the 23 covariates examined, four covariates were retained: proportion of tall buildings (% >6m in height), average air temperature (°C), average elevation (m above sea level), and average daily rainfall (mm).  
  
**Results**  
  
Results show high replacement success was mostly associated with areas with fewer tall buildings (β = -0.93 (95%CI: -1.43, -0.44), p < 0.001) and higher temperatures (β = 1.11 (95%CI: 0.59, 1.62), p < 0.001), while higher elevation and lower rainfall were associated with poorer outcomes. These associations may also reflect unmeasured socioeconomic or infrastructure variation, and context-dependent temperature effects on mosquito and Wolbachia fitness. Model-based predictions indicate non-linear dynamics, with areas of more tall buildings and higher temperatures showing divergent predicted outcomes towards either high success or failure rather than intermediate replacement. Residual spatial clustering suggests additional neighbourhood-scale processes not captured by the available covariates.  
  
**Conclusions**  
  
Outcomes in high-rise and topographically complex areas appear less likely to stabilise at intermediate replacement. Such areas may require higher release densities, targeted supplemental interventions, and more intensive monitoring, although these remain hypotheses requiring empirical evaluation. Through iterative modelling it is possible to support rapid hypothesis identification to inform field-tests and operational refinement as more evidence becomes available. These findings reinforce the role of urban permeability, vertical structure, and local environmental conditions in shaping the outcomes of Wolbachia replacement programmes.  
  
<br>
  
## The methodological workflow runs approximately:  
  
1. **Derive Wolbachia replacement trajectories**
   1. wmel_pctg_outcome.Rmd
   2. wmel_pctg_k_clustering.Rmd
   3. wmel_pctg_trajectories.Rmd

2. **Compile and process environmental covariates**
   1. model_predictors_breeding_container_definition.Rmd
   2. model_predictors.Rmd

3. **Fit the multinomial GAM and perform model selection**
   1. multinomial_gam.Rmd

4. **Run sensitivity analyses**
   1. multinomial_gam_sensitivity_forward_selection_with_resampling.Rmd
   2. multinomial_gam_sensitivity_without_trajectory_reassignment.Rmd
   3. multinomial_gam_sensitivity_bootstrapped_model_selection.Rmd
   4. multinomial_gam_sensitivity_fixed_release_zones.Rmd
   5. multinomial_gam_sensitivity_force_favelas.Rmd
   6. multinomial_gam_sensitivity_force_vegetation.Rmd
   7. multinomial_gam_sensitivity_building_height_definition.Rmd
   8. multinomial_gam_sensitivity_favela_by_elevation.Rmd
  
<br>
  
**Note:**  
- The scripts are intended to be run sequentially, however intermediate datasets are saved here to be used by subsequent analyses.  
- All required data is included in this repository, except raw Brazil 2022 Census data sourced from https://ftp.ibge.gov.br/Censos/Censo_Demografico_2022/ and household income data sourced from https://ftp.ibge.gov.br/Censos/Censo_Demografico_2022/Agregados_por_Setores_Censitarios_Rendimento_do_Responsavel/. The required files are: Agregados_por_bairros_renda_responsavel_BR.csv, Agregados_por_setores_alfabetizacao_BR.csv, Agregados_por_setores_basico_BR_20250417.csv, Agregados_por_setores_caracteristicas_domicilio2_BR_20250417.csv, RJ_bairros_CD2022.gpkg, RJ_setores_CD2022.gpkg. Also not included are the raw predictor data files GSV_container_counts.json and water_tank_density.tif, which are available upon request from Dr Steffen Knoblauch.  
- All processed predictor data is available to run the model screening script and sensitivity analyses.  
- The raw Wolbachia prevalence data for this project is sourced from https://github.com/pdgcam/wMel_Rio_dengue_chik which supports the manuscript:  
  
Ribeiro dos Santos G, Durovni B, Saraceni V, Souza Riback TI, Pinto SB, Anders KL, et al. Estimating the effect of the wMel release programme on the incidence of dengue and chikungunya in Rio de Janeiro, Brazil: A spatiotemporal modelling study. Lancet Infect Dis. 2022;22(11):1587–95. doi:10.1016/S1473-3099(22)00436-4
