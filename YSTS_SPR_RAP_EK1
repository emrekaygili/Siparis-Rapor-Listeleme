&---------------------------------------------------------------------*
*& Report  YSTS_SPR_RAP_EK1
*&
*&---------------------------------------------------------------------*
*& Satış siparişlerini raporlamak için oluşturulan programdır
*&
*&---------------------------------------------------------------------*

include ysts_spr_rap_o1_top.    " global Data

* INCLUDE YSTS_SPR_RAP_EK1                     .  " PBO-Modules
* INCLUDE YSTS_SPR_RAP_EK1                     .  " PAI-Modules
include ysts_spr_rap_o1_f01.  " FORM-Routines

start-of-selection.
  perform get_data.
  perform join_tables.
  perform alv.
