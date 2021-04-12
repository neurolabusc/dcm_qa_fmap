## About

dcm_qa_fmap is a simple DICOM to NIfTI validator script and dataset. This repository is similar to [dcm_qa](https://github.com/neurolabusc/dcm_qa), but converts direct fieldmaps. Fieldmaps can be used to undistort EPI sequences using [FSL's FUGUE](https://fsl.fmrib.ox.ac.uk/fsl/fslwiki/FUGUE/Guide#SIEMENS_data). Different scanner sequences can save fieldmapping data in different [forms](https://crnl.readthedocs.io/fieldmaps/index.html): magnitude and phase images, real and imaginary images, and direct field mapping where the scanner stores the direct estimated fieldmap (in Hz) as well as a magnitude image. Note that by adjusting the settings on a scanner console, one can store different forms of data. This repository provides direct fieldmaps from [Philips and GE scanners](https://github.com/bids-standard/bids-specification/pull/622). It also contains a script to convert these DICOM images to [BIDS-compatible](https://bids-specification--622.org.readthedocs.build/en/622/04-modality-specific-files/01-magnetic-resonance-imaging-data.html#case-3-direct-field-mapping) NIfTI images using dcm2niix (v1.0.20210410 and later).

## Data Sets

* GE/2_3db0maps s56_B0map simulated dataset
  * source: [Jaemin Shin, GE Medical](https://github.com/rordenlab/dcm2niix/issues/501)
  * (0019,109c): B0map
  * (0019,109e): B0map 
  * version: (0018,1020) 28\\LX\\MR29.1_EA_2036.a
  
* GE/3_3db0maps s57_3db0map simulated dataset
  * source: [Jaemin Shin, GE Medical](https://github.com/rordenlab/dcm2niix/issues/501)
  * (0019,109c): 3db0map
  * (0019,109e): EFGRE3D
  * version: (0018,1020) 28\\LX\\MR29.1_EA_2036.a

* GE/6_CV_Neuro s59_B0rf in-vivo brain dataset
  * source: [Jaemin Shin, GE Medical](https://github.com/rordenlab/dcm2niix/issues/501)
  * (0019,109c): B0rf
  * (0019,109e): B0map
  * version: (0018,1020) 27\\LX\\MR Software release:DV27.0_R01_1850.a
  
* Philips/fmap
  * source: [Baxter Rogers, Vanderbilt University](https://github.com/rordenlab/dcm2niix/issues/363)
  * Notes on [Philips fieldmap forms](https://github.com/rordenlab/dcm2niix/issues/455)
  * model: (0008,1090) Achieva dStream
  * version: (0018,1020) 5.3.0\5.3.0.3

## License

This software and images are open source and were acquired by National Institutes of Health. The the code is covered by the [2-clause BSD license](https://opensource.org/licenses/BSD-2-Clause).

## Versions

12-April-2021
 - Initial public release

## Running

Assuming that the executable dcm2niix is in your path, you should be able to simply run the script `batch.sh` from the terminal.

If you have problems you can edit the first few lines of the `batch.sh` script so that `basedir` reports the explicit location of the `dcm_qa_fmap` folder (by default this is assumed to be the folder containing the script) on your computer and `exenam` reports the explicit location of dcm2niix (by default it is assumed to be in your path). Also, make sure the script is executable (`chmod +x batch.sh`). Then run the script.

## Useful Links

 - Notes for [Philips](https://github.com/rordenlab/dcm2niix/tree/master/Philips) DICOM images.
 - Notes for [GE](https://github.com/rordenlab/dcm2niix/tree/master/GE) DICOM images.
 - Notes on [GE fieldmaps](https://cni.stanford.edu/wiki/GE_Processing#Kendrick.27s_Notes_on_Fieldmaps).

