*&---------------------------------------------------------------------*
*&  Include           YSTS_SPR_RAP_EK1_F01
*&---------------------------------------------------------------------*
*&---------------------------------------------------------------------*
*&      Form  GET_DATA
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
form get_data.

  select vbeln erdat ernam vkorg vtweg spart vkgrp vkbur kunnr
    from vbak into table gt_vbak
    where vbeln in s_vbeln
      and erdat in s_erdat
      and kunnr in s_kunnr.

  if gt_vbak[] is initial.
    message 'GİRİLEN KRİTERLERE İLİŞKİN KAYIT BULUNAMAMIŞTIR.' type 'E'.
  else.
    select vbeln posnr matnr matkl kwmeng vrkme
      from vbap into table gt_vbap
      for all entries in gt_vbak
      where vbeln = gt_vbak-vbeln.

  endif.

endform.
" GET_DATA
*&---------------------------------------------------------------------*
*&      Form  JOIN_TABLES
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
form join_tables .

  loop at gt_vbap assigning <fs_vbap>.
    if <fs_vbap> is assigned.
      clear gs_data.
      move-corresponding <fs_vbap> to gs_data.

      read table gt_vbak assigning <fs_vbak>
        with key vbeln = <fs_vbap>-vbeln.
      if sy-subrc is initial and <fs_vbak> is assigned.
        move-corresponding <fs_vbak> to gs_data.

      endif.

      append gs_data to gt_data.

    endif.

  endloop.
endform.                    " JOIN_TABLES

*&---------------------------------------------------------------------*
*&      Form  ALV
*&---------------------------------------------------------------------*
*       text
*----------------------------------------------------------------------*
*  -->  p1        text
*  <--  p2        text
*----------------------------------------------------------------------*
form alv .

call function 'REUSE_ALV_GRID_DISPLAY'
 EXPORTING

   I_STRUCTURE_NAME                  = 'YSTS_SPR_O'

  tables
    t_outtab                          =   gt_data
 EXCEPTIONS
   PROGRAM_ERROR                     = 1
   OTHERS                            = 2 .
if sy-subrc <> 0.
* Implement suitable error handling here
endif.




endform.                    " ALV
