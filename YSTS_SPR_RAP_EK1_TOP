*&---------------------------------------------------------------------*
*& Include YSTS_SPR_RAP_EK1_TOP                               Report YSTS_SPR_RAP_EK1
*&
*&---------------------------------------------------------------------*

report ysts_spr_rap_ek1.

tables: vbak, vbap.

data: begin of gs_vbak,"tablo kalem verilerinin tanımı
        vbeln like vbak-vbeln,
        erdat like vbak-erdat,
        ernam like vbak-ernam,
        vkorg like vbak-vkorg,
        vtweg like vbak-vtweg,
        spart like vbak-spart,
        vkgrp like vbak-vkgrp,
        vkbur like vbak-vkbur,
        kunnr like vbak-kunnr,
      end of gs_vbak.
data: begin of gs_vbap,"tablo verilerinin tanımı
        vbeln  like vbap-vbeln,
        posnr  like vbap-posnr,
        matnr  like vbap-matnr,
        matkl  like vbap-matkl,
        kwmeng like vbap-kwmeng,
        vrkme  like vbap-vrkme,
      end of gs_vbap.

data: begin of gs_data,"tabloda bulunucak verilerin tabloda tanımlanması
        vbeln  like vbak-vbeln,
        posnr  like vbap-posnr,
        erdat  like vbak-erdat,
        ernam  like vbak-ernam,
        vkorg  like vbak-vkorg,
        vtweg  like vbak-vtweg,
        spart  like vbak-spart,
        vkgrp  like vbak-vkgrp,
        vkbur  like vbak-vkbur,
        kunnr  like vbak-kunnr,
        matnr  like vbap-matnr,
        matkl  like vbap-matkl,
        kwmeng like vbap-kwmeng,
        vrkme  like vbap-vrkme,
      end of gs_data.
data: gt_vbak like table of gs_vbak,    "Tablolar tanımlanır
      gt_vbap like table of gs_vbap,
      gt_data like table of gs_data.

field-symbols: <fs_vbak> like line of gt_vbak,
               <fs_vbap> like line of gt_vbap,
               <fs_data> like line of gt_data.

select-options: s_vbeln for vbak-vbeln,
                s_erdat for vbak-erdat,
                s_kunnr for vbak-kunnr.
