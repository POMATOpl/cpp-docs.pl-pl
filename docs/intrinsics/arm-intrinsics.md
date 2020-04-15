---
title: Funkcje wewnętrzne ARM
ms.date: 09/02/2019
f1_keywords:
- arm_neon/vsetq_lane_p8
- armintr/_arm_uxtb
- arm_neon/vld4_lane_p8
- arm_neon/vrshrn_n_s64
- arm_neon/vsli_n_u32
- arm_neon/vsraq_n_u16
- arm_neon/vcgt_f32
- armintr/__iso_volatile_store32
- arm_neon/vceqq_f32
- armintr/_arm_smlal
- arm_neon/vmull_n_s32
- arm_neon/vmax_s8
- arm_neon/vmvn_u32
- arm_neon/vrshl_u32
- arm_neon/int32x2_t
- arm_neon/vdupq_n_p8
- arm_neon/vpmax_u16
- arm_neon/vtrnq_s32
- arm_neon/vset_lane_f32
- arm_neon/vrev64_s8
- arm_neon/vtrnq_p8
- arm_neon/vqshlq_u64
- arm_neon/vld1q_dup_s64
- arm_neon/vmovq_n_u64
- arm_neon/vqshrn_n_u16
- arm_neon/vhadd_s32
- arm_neon/vrhaddq_u32
- arm_neon/vst1q_p8
- arm_neon/vshrn_n_s16
- arm_neon/vget_high_f32
- arm_neon/vuzpq_s16
- arm_neon/vand_u16
- arm_neon/vmulq_s32
- arm_neon/vrsraq_n_s64
- arm_neon/vceqq_s8
- arm_neon/uint64x1x3_t
- arm_neon/veor_u32
- armintr/_arm_pkhtb
- arm_neon/vorrq_u16
- arm_neon/vpaddl_s8
- arm_neon/vmla_n_s16
- arm_neon/vqdmlal_lane_s32
- arm_neon/vshlq_n_u8
- arm_neon/vst2_lane_p8
- arm_neon/vld3q_u16
- arm_neon/vandq_u8
- arm_neon/vst1_u64
- arm_neon/vaddq_s64
- arm_neon/vuzpq_u32
- arm_neon/vld3_lane_p8
- arm_neon/vminq_s32
- arm_neon/vabd_u16
- arm_neon/vdup_n_u32
- arm_neon/vmul_p8
- arm_neon/vsra_n_u16
- arm_neon/vst3q_u16
- arm_neon/int32x2x3_t
- arm_neon/vld2_dup_u16
- arm_neon/vrhaddq_u8
- arm_neon/vhadd_u8
- arm_neon/vgetq_lane_s32
- arm_neon/vcleq_u16
- arm_neon/vabdq_s8
- arm_neon/vrev16q_u8
- arm_neon/vqshlu_n_s64
- arm_neon/vcvt_n_s32_f32
- arm_neon/vqrshrn_n_s64
- arm_neon/vst1q_p16
- arm_neon/vgetq_lane_s16
- arm_neon/vtstq_u32
- arm_neon/vmlsl_n_s16
- arm_neon/vcge_s8
- arm_neon/vshr_n_s16
- armintr/_arm_rbit
- arm_neon/vmls_u32
- arm_neon/vmls_lane_u32
- arm_neon/vcvtq_n_s32_f32
- arm_neon/vqshl_n_s8
- arm_neon/vst1q_s16
- armintr/__emit
- arm_neon/vshlq_s64
- arm_neon/vuzp_s8
- arm_neon/vld1q_lane_s64
- arm_neon/veorq_s32
- arm_neon/vaddq_u64
- arm_neon/vceq_s32
- arm_neon/vmovn_u16
- arm_neon/vabal_s8
- arm_neon/vabsq_f32
- armintr/_arm_smuad
- arm_neon/veor_u8
- arm_neon/int16x4_t
- arm_neon/vsraq_n_s16
- arm_neon/vshlq_s8
- arm_neon/vcreate_u32
- arm_neon/vzipq_s8
- arm_neon/vst3q_u8
- arm_neon/int64x1x4_t
- armintr/__iso_volatile_store16
- arm_neon/vst4_lane_p16
- arm_neon/vld1_dup_p16
- arm_neon/vhadd_s16
- arm_neon/vtbl2_s8
- arm_neon/veorq_u32
- arm_neon/vqdmlal_lane_s16
- arm_neon/vrsra_n_u8
- arm_neon/vbslq_u16
- arm_neon/vget_low_s64
- arm_neon/vceq_u16
- arm_neon/vdupq_lane_u32
- arm_neon/vabdl_u32
- arm_neon/vmlal_s32
- arm_neon/vst1_lane_u8
- arm_neon/vld4q_f16
- arm_neon/vqdmlsl_s32
- arm_neon/vqrdmulh_s32
- arm_neon/vqrshl_u8
- arm_neon/uint32x4x4_t
- arm_neon/vabaq_u16
- arm_neon/vcnt_p8
- arm_neon/vld3q_s16
- arm_neon/vshl_n_u32
- arm_neon/vrev64q_u16
- arm_neon/vextq_s64
- arm_neon/vhsubq_s8
- arm_neon/vld2_dup_u8
- arm_neon/vst3_s16
- arm_neon/vorn_u16
- arm_neon/vst4_f16
- arm_neon/vpadalq_u8
- armintr/__iso_volatile_load8
- arm_neon/vmovl_u16
- arm_neon/vld4q_u32
- arm_neon/vcgt_u32
- arm_neon/vmlaq_n_u32
- arm_neon/vrsra_n_u64
- arm_neon/vst4_s8
- arm_neon/vcvtq_n_f32_u32
- arm_neon/vst2q_u16
- arm_neon/vqshrn_n_s16
- arm_neon/vld4_s16
- arm_neon/uint16x8x4_t
- arm_neon/vrsqrte_u32
- arm_neon/vcltq_s8
- arm_neon/vst3_u16
- arm_neon/vst2_f32
- arm_neon/vld2_u64
- arm_neon/vst1_u16
- arm_neon/vmls_s16
- arm_neon/vqrshlq_s32
- arm_neon/vqdmull_s16
- arm_neon/vld2_lane_p16
- arm_neon/vpaddlq_u8
- arm_neon/vcvt_n_f32_u32
- arm_neon/vcgtq_u8
- arm_neon/vshl_s32
- arm_neon/vtbx3_p8
- arm_neon/vld3_dup_s32
- arm_neon/int16x4x3_t
- arm_neon/vcale_f32
- arm_neon/vqabsq_s32
- arm_neon/vmulq_u16
- arm_neon/vst1_s8
- arm_neon/vclt_u8
- armintr/_arm_sxtb16
- arm_neon/vshr_n_s8
- arm_neon/vst1_lane_f16
- arm_neon/vorn_s64
- armintr/_arm_usub8
- arm_neon/vst4_lane_f32
- arm_neon/vmls_lane_u16
- arm_neon/vpaddl_u32
- arm_neon/vdup_lane_u64
- arm_neon/vsri_n_p16
- arm_neon/vqrshlq_u64
- arm_neon/vclz_s16
- arm_neon/vsra_n_u32
- arm_neon/vabaq_s8
- arm_neon/vst2_lane_s8
- arm_neon/vcvt_n_u32_f32
- arm_neon/vst3_u32
- arm_neon/vcvtq_f32_u32
- arm_neon/vraddhn_s64
- armintr/_arm_uqsax
- arm_neon/vshl_u8
- armintr/_arm_uqadd16
- arm_neon/vrsra_n_u16
- arm_neon/vrshl_u64
- arm_neon/int32x4x3_t
- arm_neon/vmull_u8
- arm_neon/vcombine_u64
- arm_neon/vmull_u16
- arm_neon/vld1_dup_s8
- armintr/_CountLeadingSigns64
- arm_neon/vqshlq_n_s32
- arm_neon/vrecpe_f32
- arm_neon/vsri_n_u32
- arm_neon/vrsraq_n_s8
- arm_neon/vsetq_lane_s16
- arm_neon/vget_high_u32
- arm_neon/vmlal_u32
- arm_neon/vdupq_lane_s16
- arm_neon/vsubq_u64
- arm_neon/vext_p8
- arm_neon/vshl_u16
- arm_neon/vmls_n_u16
- arm_neon/vmull_s16
- arm_neon/vmovq_n_s64
- arm_neon/vaddq_f32
- arm_neon/vshl_n_s16
- arm_neon/vext_p16
- arm_neon/vextq_u32
- arm_neon/vld1_p8
- arm_neon/veor_s32
- arm_neon/int16x8x4_t
- arm_neon/vst1q_u16
- arm_neon/vzipq_p8
- arm_neon/int32x4x4_t
- arm_neon/vqdmulhq_lane_s32
- arm_neon/vst3_lane_u32
- arm_neon/vhsubq_s32
- armintr/__static_assert
- arm_neon/vst3q_lane_u16
- arm_neon/vpmin_u32
- arm_neon/vrev64q_p16
- arm_neon/vcleq_f32
- arm_neon/vhsub_u16
- arm_neon/vld2_lane_s32
- arm_neon/vmlsl_s32
- armintr/_arm_rev
- arm_neon/vcgeq_s16
- arm_neon/vmulq_s8
- arm_neon/vsri_n_s8
- arm_neon/vpadd_f32
- arm_neon/vld1q_lane_f16
- arm_neon/vmls_u16
- arm_neon/vld1_lane_f32
- arm_neon/vmlaq_lane_s16
- arm_neon/vqadd_u32
- arm_neon/vmul_n_s32
- arm_neon/vld1q_dup_p8
- arm_neon/vtrnq_s8
- arm_neon/vbslq_p8
- arm_neon/vget_lane_s8
- arm_neon/vext_u16
- arm_neon/vsubq_s16
- arm_neon/vld4_lane_s8
- arm_neon/uint32x2x2_t
- arm_neon/vdup_n_s8
- arm_neon/vld4_lane_u16
- arm_neon/vmovq_n_s16
- arm_neon/vst4q_s32
- arm_neon/vst2q_f16
- arm_neon/vbslq_s16
- arm_neon/vand_u64
- arm_neon/poly16_t
- arm_neon/vaba_u16
- arm_neon/vqshlq_s64
- armintr/_arm_uxth
- arm_neon/vst2_lane_s16
- arm_neon/vand_u8
- arm_neon/int8x16x3_t
- arm_neon/vrev64_u16
- arm_neon/vld2_lane_s16
- arm_neon/vabaq_s16
- arm_neon/vsli_n_u8
- arm_neon/vsraq_n_u64
- arm_neon/vmlsl_s16
- arm_neon/vmovn_u64
- arm_neon/vld4_f32
- arm_neon/vst2q_f32
- arm_neon/vtbx3_u8
- arm_neon/vcombine_s8
- arm_neon/vqdmulhq_s32
- arm_neon/vgetq_lane_p8
- armintr/_arm_smusd
- arm_neon/vpmax_u32
- arm_neon/vceq_f32
- arm_neon/vsri_n_p8
- arm_neon/vhsubq_u8
- arm_neon/vuzp_s16
- arm_neon/uint32x2x4_t
- arm_neon/vst4_lane_s32
- arm_neon/vsli_n_p8
- arm_neon/vld3_lane_f16
- arm_neon/vbic_u64
- arm_neon/vmlal_u16
- arm_neon/vmvn_s8
- arm_neon/vtstq_s8
- arm_neon/vmaxq_s32
- arm_neon/vqmovn_u64
- armintr/_arm_ssax
- arm_neon/vext_u32
- arm_neon/vld1_dup_u64
- arm_neon/vmlal_n_s16
- armintr/_arm_smulbb
- arm_neon/vqrdmulhq_lane_s16
- arm_neon/vdup_n_p8
- arm_neon/vaba_s8
- arm_neon/vrshrq_n_s32
- arm_neon/vmvnq_s32
- arm_neon/vpadal_s32
- arm_neon/vqshl_s16
- arm_neon/vtrn_p8
- arm_neon/vzip_s16
- arm_neon/vcge_f32
- armintr/_arm_sxtab16
- arm_neon/vst1q_lane_u64
- arm_neon/vqrshlq_u16
- arm_neon/int8x8_t
- arm_neon/vorr_u8
- arm_neon/vrev64_f32
- arm_neon/vpaddlq_s16
- arm_neon/vdupq_lane_u64
- arm_neon/vcltq_u16
- arm_neon/vst3_lane_f32
- arm_neon/vld2_dup_f32
- armintr/_arm_smmul
- arm_neon/vbsl_s16
- arm_neon/vld1_lane_u8
- arm_neon/vld2q_lane_u16
- arm_neon/vqshlu_n_s32
- armintr/_arm_smlalbt
- arm_neon/vmla_s8
- arm_neon/vsli_n_p16
- arm_neon/vmla_u8
- arm_neon/vqaddq_s16
- arm_neon/vld3_p16
- arm_neon/uint64x2x4_t
- arm_neon/vcnt_u8
- arm_neon/vcltq_u8
- arm_neon/vtbx1_p8
- arm_neon/vrev32q_u16
- arm_neon/vld1_lane_u16
- arm_neon/vqadd_s16
- arm_neon/vcnt_s8
- armintr/_MulUnsignedHigh
- arm_neon/vsliq_n_u8
- arm_neon/vpmin_s16
- armintr/__iso_volatile_load16
- arm_neon/vst2_lane_f32
- arm_neon/vqsubq_s32
- arm_neon/vqshl_s32
- arm_neon/vsraq_n_u32
- arm_neon/vcreate_s32
- arm_neon/vld3q_lane_u32
- arm_neon/vaddq_u16
- arm_neon/vand_s32
- arm_neon/vbicq_s32
- armintr/_arm_smulbt
- arm_neon/vrsra_n_s8
- arm_neon/vshrq_n_u32
- arm_neon/vld4_f16
- arm_neon/vcagtq_f32
- arm_neon/vaddw_u32
- armintr/_arm_uxtah
- arm_neon/vtstq_u8
- arm_neon/vld1_dup_u16
- arm_neon/int16x4x4_t
- arm_neon/vqshluq_n_s8
- arm_neon/vqdmulhq_n_s32
- arm_neon/vst1_s64
- arm_neon/vrsubhn_u16
- arm_neon/vld4_dup_p16
- arm_neon/vmlaq_s32
- arm_neon/vnegq_s32
- arm_neon/vst2q_u8
- arm_neon/vget_low_s32
- arm_neon/vorn_u32
- arm_neon/vld1q_s8
- arm_neon/vandq_s64
- arm_neon/vmvn_p8
- arm_neon/vabdl_s16
- arm_neon/vqshl_u32
- arm_neon/vld3_dup_u16
- arm_neon/vmov_n_f32
- arm_neon/vcvt_f32_u32
- arm_neon/vrhadd_s8
- arm_neon/vpadal_u32
- armintr/_arm_ubfx
- arm_neon/vcgt_s8
- arm_neon/vget_lane_f32
- arm_neon/vcge_s16
- arm_neon/vmov_n_s64
- arm_neon/vmulq_n_f32
- arm_neon/vpadalq_u32
- armintr/_arm_smlaldx
- arm_neon/vtst_u16
- arm_neon/vmls_n_s16
- arm_neon/vcombine_f32
- arm_neon/vld1q_p16
- armintr/_arm_ssat
- arm_neon/vextq_s8
- arm_neon/vmax_u32
- arm_neon/vqsubq_s64
- arm_neon/vcltq_s16
- arm_neon/vst2q_s8
- arm_neon/vpmax_u8
- arm_neon/vld4_dup_p8
- arm_neon/vrshr_n_u64
- arm_neon/vqrshrun_n_s16
- arm_neon/vget_low_u64
- arm_neon/vst2q_s32
- arm_neon/vst4_s32
- arm_neon/vrshrq_n_u8
- arm_neon/vdupq_n_u64
- arm_neon/vsriq_n_u8
- arm_neon/vdupq_lane_u8
- arm_neon/vsriq_n_s64
- arm_neon/vget_low_u8
- arm_neon/vst1_lane_p16
- arm_neon/vld1q_lane_u8
- arm_neon/vcgt_s32
- arm_neon/vst1_lane_u32
- arm_neon/vzipq_p16
- arm_neon/vmvn_u16
- arm_neon/vld1q_lane_u16
- armintr/_MoveToCoprocessor64
- arm_neon/vdup_n_u16
- arm_neon/vzipq_f32
- arm_neon/vshl_s16
- arm_neon/vmlaq_n_s16
- arm_neon/vget_lane_s64
- arm_neon/vld1q_lane_f32
- arm_neon/vnegq_s16
- armintr/_arm_usax
- arm_neon/vabd_s16
- arm_neon/vmovq_n_u32
- arm_neon/vshlq_n_u16
- armintr/_CountLeadingSigns
- arm_neon/vld3q_f16
- arm_neon/vceqq_u32
- arm_neon/int8x8x2_t
- arm_neon/vst2_s64
- arm_neon/vst4q_lane_s16
- arm_neon/vorn_s32
- arm_neon/vcle_f32
- arm_neon/vld1_p16
- arm_neon/vtrn_u32
- arm_neon/vbsl_s32
- arm_neon/float32x2_t
- arm_neon/vmvn_s32
- arm_neon/vqdmlsl_lane_s16
- arm_neon/vtbl3_s8
- arm_neon/vsra_n_u8
- arm_neon/vcvtq_u32_f32
- arm_neon/vst1_p8
- arm_neon/vrev64_p16
- armintr/__ldrexd
- arm_neon/vcgeq_u8
- arm_neon/vmlal_n_s32
- arm_neon/vst1q_lane_p8
- arm_neon/vpadalq_s32
- arm_neon/vtstq_p8
- arm_neon/vld4_lane_u8
- armintr/_arm_ssub16
- arm_neon/vpaddlq_u16
- armintr/_arm_udiv
- arm_neon/vld1_lane_p8
- arm_neon/vst1q_u32
- arm_neon/vld1_f32
- arm_neon/uint64x2x2_t
- arm_neon/vqsubq_u64
- arm_neon/vld4q_s32
- arm_neon/vceq_s16
- arm_neon/vst3_s64
- arm_neon/vext_s8
- armintr/_arm_smlsd
- arm_neon/vpadal_s16
- arm_neon/vbic_s32
- arm_neon/vld1_dup_u8
- arm_neon/vclt_f32
- arm_neon/vrev64_s16
- arm_neon/vrshlq_s64
- arm_neon/vdupq_n_s64
- arm_neon/vuzp_p16
- arm_neon/vld3_dup_p16
- arm_neon/vcreate_s8
- armintr/_arm_smlatt
- arm_neon/vtst_s32
- arm_neon/vshrq_n_s64
- arm_neon/vqshlq_n_s64
- arm_neon/vqshlu_n_s16
- arm_neon/vcleq_s16
- arm_neon/vmull_lane_s16
- arm_neon/int32x4_t
- arm_neon/vqadd_s8
- arm_neon/vld2q_f16
- arm_neon/vld2q_lane_p16
- arm_neon/vadd_u32
- arm_neon/vcntq_u8
- arm_neon/vst1_f32
- arm_neon/vmaxq_u32
- arm_neon/vsub_u64
- arm_neon/vsubl_s32
- arm_neon/poly16x4_t
- arm_neon/vgetq_lane_u16
- arm_neon/vdup_lane_s32
- arm_neon/vrhadd_s32
- arm_neon/veorq_u8
- arm_neon/vclzq_s8
- arm_neon/vsliq_n_s64
- arm_neon/vpadalq_s16
- arm_neon/vmla_n_f32
- arm_neon/vcgt_u16
- armintr/_arm_usada8
- arm_neon/vabd_u32
- arm_neon/vgetq_lane_s8
- arm_neon/vqshlq_n_u64
- arm_neon/vabaq_u32
- armintr/_arm_uhsax
- arm_neon/vmulq_f32
- arm_neon/vld3_dup_s16
- arm_neon/vst3_f16
- arm_neon/vrshrq_n_s64
- armintr/__rdpmccntr64
- arm_neon/vclsq_s32
- arm_neon/vmax_u16
- arm_neon/vmvnq_p8
- arm_neon/veor_u16
- arm_neon/vqshrn_n_u32
- arm_neon/vextq_u64
- arm_neon/vld1q_f32
- arm_neon/vget_low_u32
- arm_neon/vhaddq_s32
- arm_neon/vminq_u16
- arm_neon/vqrdmulhq_lane_s32
- arm_neon/vmla_s16
- arm_neon/vadd_s16
- arm_neon/vbsl_u16
- arm_neon/vhsub_s8
- arm_neon/vld4q_lane_p16
- arm_neon/vld1_s16
- arm_neon/vst2q_lane_p16
- arm_neon/vld2_dup_s8
- arm_neon/vst3q_s16
- arm_neon/vcgeq_u32
- arm_neon/vabdq_s16
- arm_neon/vrhadd_u16
- arm_neon/vqshlq_n_u32
- arm_neon/vst4q_lane_u32
- arm_neon/vrsraq_n_u64
- arm_neon/vmlsq_n_s32
- arm_neon/vld4_u8
- arm_neon/vld2_f16
- arm_neon/vqshlq_u8
- arm_neon/vorrq_u64
- arm_neon/vmin_u16
- arm_neon/vext_u8
- arm_neon/vpaddl_s32
- arm_neon/vshlq_u64
- arm_neon/vst2q_lane_f16
- armintr/_arm_sbfx
- arm_neon/vld3_dup_f16
- armintr/_arm_uhasx
- arm_neon/vst2_lane_u8
- armintr/_arm_smultb
- arm_neon/vdup_n_p16
- arm_neon/vtrnq_u32
- arm_neon/vrshlq_u8
- arm_neon/vld4_lane_p16
- arm_neon/vsraq_n_s32
- arm_neon/vclt_s16
- arm_neon/vzip_u8
- arm_neon/vld3_lane_s16
- arm_neon/vceqq_s32
- arm_neon/vld3_dup_f32
- arm_neon/vld4q_lane_s32
- arm_neon/poly8x16x4_t
- arm_neon/uint64x1x2_t
- arm_neon/vqdmlal_n_s16
- arm_neon/vld2_dup_f16
- arm_neon/vshrq_n_s32
- arm_neon/vcleq_s8
- arm_neon/vld3_s32
- arm_neon/vqrshlq_s64
- arm_neon/vbsl_f32
- arm_neon/vext_s64
- arm_neon/vabaq_s32
- arm_neon/vmulq_s16
- arm_neon/vld3_lane_u16
- arm_neon/vld3q_lane_u16
- armintr/_arm_smlaltt
- arm_neon/poly8x8x2_t
- arm_neon/vst3q_u32
- armintr/_arm_smlsdx
- arm_neon/vqrshl_s64
- arm_neon/vextq_p8
- armintr/_arm_uhsub16
- arm_neon/vld3q_p8
- armintr/_arm_smlawt
- armintr/_arm_smlawb
- arm_neon/vdupq_lane_s8
- arm_neon/vaddl_s16
- arm_neon/vcombine_p16
- arm_neon/vzipq_u32
- arm_neon/poly16x8_t
- arm_neon/vshlq_n_s32
- arm_neon/vrshl_s8
- arm_neon/vst2_u64
- arm_neon/vrev64q_s8
- arm_neon/vst2q_lane_s32
- arm_neon/vld2_dup_s16
- arm_neon/vclt_u16
- arm_neon/vuzp_p8
- arm_neon/vshrq_n_s16
- arm_neon/vst3_u64
- arm_neon/vpmin_u16
- arm_neon/vld3q_lane_s32
- arm_neon/vmlal_s16
- arm_neon/poly16x4x4_t
- arm_neon/vorr_u16
- arm_neon/vsliq_n_s16
- arm_neon/vaddl_u8
- arm_neon/vld4_dup_s32
- arm_neon/vld2_f32
- arm_neon/vclt_u32
- arm_neon/vmull_lane_u16
- arm_neon/vsubw_u32
- arm_neon/vld2_dup_s32
- arm_neon/vuzp_s32
- arm_neon/vcge_s32
- arm_neon/vdup_lane_p16
- arm_neon/vpmin_s8
- arm_neon/vpaddlq_u32
- arm_neon/vmlaq_n_s32
- arm_neon/vshrn_n_u64
- arm_neon/vrshr_n_u16
- arm_neon/vld1_s64
- arm_neon/vbsl_u64
- armintr/_arm_smlad
- arm_neon/vqsub_s16
- arm_neon/vld4_p8
- arm_neon/vqdmulh_lane_s32
- arm_neon/vld3_dup_s64
- arm_neon/vornq_s32
- arm_neon/vpadd_u8
- arm_neon/vld3_lane_p16
- arm_neon/uint64x1x4_t
- arm_neon/vld3_u16
- armintr/_arm_shsax
- arm_neon/vabdq_u16
- arm_neon/vcgtq_f32
- arm_neon/vsubq_s8
- arm_neon/vget_low_f16
- arm_neon/vld4_dup_u64
- arm_neon/vst3_lane_s8
- armintr/_arm_ssat16
- arm_neon/vmlaq_f32
- arm_neon/vsri_n_s32
- arm_neon/vmax_u8
- arm_neon/vqadd_u8
- armintr/_arm_uqsub8
- armintr/_arm_clz
- arm_neon/vcgtq_s32
- arm_neon/vraddhn_s32
- arm_neon/vzip_s8
- arm_neon/veorq_s16
- arm_neon/vsetq_lane_s32
- arm_neon/vmul_n_u16
- armintr/_ReadBankedReg
- arm_neon/vld1q_u8
- arm_neon/vld4_p16
- arm_neon/int64x2x2_t
- arm_neon/vmaxq_s8
- arm_neon/vpmax_s16
- arm_neon/vshlq_u16
- arm_neon/vtrnq_p16
- arm_neon/vabal_u16
- arm_neon/vld2_lane_u16
- arm_neon/vrev32_u8
- arm_neon/vrshl_s32
- arm_neon/vget_low_f32
- arm_neon/vld2_s8
- arm_neon/vclzq_s16
- arm_neon/vqdmulhq_n_s16
- arm_neon/vset_lane_u64
- arm_neon/vld2_dup_p16
- arm_neon/vpaddlq_s32
- arm_neon/vld2q_p8
- arm_neon/vst3_lane_u8
- arm_neon/vld4_dup_f32
- arm_neon/vld2_s64
- arm_neon/vmls_u8
- arm_neon/vtbx4_u8
- arm_neon/vsetq_lane_f32
- arm_neon/vcvt_s32_f32
- arm_neon/vst3q_s32
- arm_neon/vmlsq_s8
- arm_neon/vmlaq_n_u16
- armintr/__iso_volatile_load64
- arm_neon/vcgt_u8
- arm_neon/vld2_dup_p8
- arm_neon/vmov_n_u8
- armintr/_arm_sasx
- arm_neon/vmovq_n_p16
- arm_neon/vmlaq_u32
- arm_neon/vst3_f32
- arm_neon/int32x2x4_t
- arm_neon/vld1q_lane_u64
- arm_neon/vclz_u16
- arm_neon/uint8x8_t
- arm_neon/vsub_u32
- arm_neon/vorn_u8
- armintr/__wfe
- arm_neon/vget_high_s16
- arm_neon/vzip_p8
- arm_neon/vmlal_lane_s16
- arm_neon/vmulq_u8
- armintr/_isunordered
- arm_neon/vld1_dup_f32
- arm_neon/vld4_lane_s16
- arm_neon/vdupq_n_s16
- arm_neon/vst3q_p16
- arm_neon/vst1_lane_f32
- arm_neon/float32x4x3_t
- arm_neon/vand_s8
- arm_neon/float32x2x4_t
- arm_neon/vld3_p8
- arm_neon/vmlaq_lane_u16
- armintr/_arm_uqsub16
- arm_neon/vget_high_s32
- arm_neon/vshl_n_s32
- arm_neon/vornq_s8
- arm_neon/vmlsl_n_u32
- arm_neon/vqshlq_n_s8
- arm_neon/int32x2x2_t
- arm_neon/int16x4x2_t
- arm_neon/vceqq_u8
- arm_neon/vcreate_f16
- arm_neon/vorn_s16
- arm_neon/vqmovn_s32
- arm_neon/vextq_u8
- arm_neon/vld4_s32
- armintr/_WriteStatusReg
- arm_neon/uint8x16_t
- arm_neon/vshrn_n_s64
- arm_neon/vmul_n_u32
- arm_neon/vabdl_u8
- arm_neon/vtbx3_s8
- arm_neon/vaddhn_s16
- arm_neon/vld3q_s8
- arm_neon/vmlsl_n_u16
- arm_neon/vrev64q_s32
- arm_neon/int16x8_t
- arm_neon/vext_s32
- arm_neon/vdupq_n_f32
- arm_neon/vld1q_lane_s32
- arm_neon/vqrshlq_u32
- arm_neon/vtbl2_u8
- arm_neon/vgetq_lane_u8
- arm_neon/veorq_u64
- arm_neon/vcntq_s8
- arm_neon/vbslq_p16
- arm_neon/vqnegq_s32
- arm_neon/vaddw_s32
- arm_neon/vmov_n_p8
- arm_neon/vmull_p8
- arm_neon/vld1_lane_u32
- arm_neon/vcombine_s16
- arm_neon/vqshrn_n_s64
- arm_neon/vceqq_s16
- arm_neon/vld4q_p16
- armintr/_ReadStatusReg
- armintr/_arm_qdadd
- arm_neon/uint32x4x2_t
- arm_neon/vcleq_u8
- armintr/_arm_sxtah
- arm_neon/vrhaddq_s32
- arm_neon/vset_lane_s64
- arm_neon/vld4_s64
- armintr/_DAddSatInt
- arm_neon/vorr_s8
- arm_neon/vst2_u32
- arm_neon/vshll_n_u16
- arm_neon/vld2_dup_u32
- arm_neon/vst3q_lane_s32
- arm_neon/vst3q_p8
- armintr/_MoveFromCoprocessor
- arm_neon/uint32x4_t
- arm_neon/vuzpq_s8
- arm_neon/vrecps_f32
- arm_neon/vst1_lane_s8
- arm_neon/vtbx1_s8
- arm_neon/uint16x8x3_t
- arm_neon/vpaddl_s16
- arm_neon/vsubq_s64
- arm_neon/vrsraq_n_u8
- arm_neon/vqadd_s64
- arm_neon/vst4_lane_s16
- arm_neon/vqadd_u16
- arm_neon/vset_lane_u32
- arm_neon/vand_u32
- arm_neon/vrsqrtsq_f32
- arm_neon/vqaddq_u32
- arm_neon/vsra_n_s64
- armintr/_arm_umlal
- arm_neon/vcvt_f32_f16
- arm_neon/vget_lane_u32
- arm_neon/vbsl_s8
- arm_neon/vrshlq_u32
- arm_neon/vqdmull_lane_s16
- arm_neon/vabsq_s32
- arm_neon/vld3_s8
- arm_neon/vst3q_lane_s16
- arm_neon/vld2q_lane_s16
- arm_neon/vst1_lane_s64
- arm_neon/vmov_n_u16
- arm_neon/vst4_lane_u8
- arm_neon/vshll_n_u32
- arm_neon/vqabs_s8
- arm_neon/vmvnq_u8
- arm_neon/vpadalq_u16
- arm_neon/vbsl_p16
- arm_neon/vqrshrn_n_u16
- arm_neon/vld3q_u32
- arm_neon/vcgeq_f32
- armintr/__iso_volatile_load32
- arm_neon/vrecpe_u32
- arm_neon/vld2_dup_u64
- arm_neon/vld3q_f32
- armintr/_arm_shsub8
- arm_neon/vdup_lane_s64
- arm_neon/vqrshl_s8
- arm_neon/vsliq_n_u16
- arm_neon/vld1q_u16
- arm_neon/vorr_u32
- arm_neon/vqrshl_s32
- armintr/__dmb
- arm_neon/veorq_s8
- arm_neon/vld1_u16
- arm_neon/vmov_n_u32
- arm_neon/vhsub_s16
- arm_neon/vst4q_lane_u16
- arm_neon/vbsl_u8
- armintr/_arm_uxtab
- arm_neon/vld2q_lane_f32
- arm_neon/vst2_p8
- armintr/_arm_smmla
- arm_neon/vaddw_u16
- arm_neon/vmlal_s8
- arm_neon/vtst_u32
- arm_neon/vtbl4_u8
- arm_neon/vcvt_n_f32_s32
- arm_neon/vcageq_f32
- arm_neon/vget_low_s16
- arm_neon/vdupq_n_u8
- arm_neon/vorn_s8
- arm_neon/uint8x16x3_t
- arm_neon/vabdq_u32
- arm_neon/vrev64_p8
- arm_neon/vqsubq_s8
- armintr/_arm_smlabb
- arm_neon/vbicq_s64
- arm_neon/vmaxq_u16
- arm_neon/vdup_n_u8
- arm_neon/veor_s8
- arm_neon/int16x8x2_t
- arm_neon/vcvtq_s32_f32
- arm_neon/vtrn_u16
- arm_neon/vbslq_s32
- arm_neon/vld1q_dup_u32
- arm_neon/vmul_n_f32
- arm_neon/vqrshl_u32
- arm_neon/vqsubq_s16
- arm_neon/vst2_lane_f16
- armintr/_arm_smulwt
- arm_neon/vrshrn_n_u32
- arm_neon/vget_high_p16
- arm_neon/vqadd_u64
- arm_neon/vsli_n_s32
- arm_neon/vhadd_u32
- arm_neon/vmlsl_lane_u16
- arm_neon/vclzq_u32
- arm_neon/vqshrun_n_s64
- arm_neon/vrev64q_u32
- arm_neon/vqshrun_n_s16
- arm_neon/vrev32q_s8
- armintr/_arm_shasx
- arm_neon/vaddl_s8
- armintr/_arm_smull
- arm_neon/vabaq_u8
- armintr/_arm_revsh
- arm_neon/vsubq_f32
- arm_neon/poly16x4x2_t
- arm_neon/poly8x8x3_t
- arm_neon/vsubhn_s64
- arm_neon/vcle_u16
- arm_neon/poly8x16x3_t
- arm_neon/vqdmlsl_n_s16
- arm_neon/vqshl_u64
- arm_neon/vcge_u16
- armintr/_arm_uasx
- arm_neon/vmovl_s32
- arm_neon/vst1q_lane_u16
- arm_neon/vbic_u32
- arm_neon/vld2_s16
- armintr/_arm_qasx
- arm_neon/vorrq_u8
- arm_neon/vst2_s32
- armintr/_WriteBankedReg
- arm_neon/veorq_s64
- arm_neon/vld4_lane_f32
- arm_neon/vcreate_u8
- arm_neon/vset_lane_u8
- arm_neon/vandq_u16
- arm_neon/vrsubhn_s64
- arm_neon/vst1q_lane_p16
- arm_neon/uint8x8x2_t
- arm_neon/vmlsl_s8
- arm_neon/vmax_s32
- arm_neon/uint32x4x3_t
- arm_neon/vld4_dup_u16
- arm_neon/vabs_s32
- arm_neon/vld3_dup_u32
- arm_neon/vrshl_u16
- arm_neon/vcle_u8
- arm_neon/vqshl_n_u16
- arm_neon/vbic_s8
- arm_neon/float32x4x2_t
- arm_neon/vmls_f32
- arm_neon/vshll_n_u8
- arm_neon/vminq_s8
- arm_neon/vmlsq_lane_f32
- arm_neon/vst1q_f16
- arm_neon/vst1_lane_u64
- arm_neon/vrhadd_u8
- arm_neon/vclt_s32
- arm_neon/vst2_p16
- arm_neon/vrshrq_n_u16
- arm_neon/vneg_s32
- arm_neon/vmovl_s16
- arm_neon/vqshlq_s8
- arm_neon/vld1_s8
- arm_neon/vqdmulh_s32
- arm_neon/vcls_s8
- armintr/__trap
- arm_neon/vuzp_u32
- armintr/_CopyInt64FromDouble
- arm_neon/int8x16x2_t
- arm_neon/vmovn_s32
- arm_neon/vget_high_s8
- arm_neon/veor_s64
- armintr/_arm_uadd8
- arm_neon/vrev16_u8
- arm_neon/vbicq_u64
- arm_neon/vst4_lane_f16
- arm_neon/vst3_s32
- arm_neon/poly8x8_t
- arm_neon/vtstq_u16
- arm_neon/vld1_lane_s8
- arm_neon/float32x4x4_t
- arm_neon/vst2_s16
- arm_neon/vqrdmulhq_s32
- arm_neon/vqdmulhq_s16
- arm_neon/vrshrq_n_s8
- arm_neon/vcle_s32
- arm_neon/vtbl3_p8
- arm_neon/vbslq_u8
- arm_neon/vst4_u64
- armintr/_arm_umaal
- arm_neon/vshll_n_s8
- arm_neon/vcvt_u32_f32
- arm_neon/vld4q_p8
- arm_neon/vsetq_lane_u16
- arm_neon/vabd_u8
- arm_neon/vclz_u8
- arm_neon/vsubq_u32
- arm_neon/vld1q_lane_p16
- arm_neon/vcgtq_s16
- arm_neon/vmla_lane_s32
- arm_neon/vshlq_n_s64
- arm_neon/vbsl_u32
- arm_neon/vqshlq_s16
- armintr/_arm_qadd8
- arm_neon/vrshr_n_s32
- armintr/_CountOneBits64
- arm_neon/vceq_u32
- arm_neon/vbsl_p8
- arm_neon/uint16x8x2_t
- arm_neon/vsli_n_s16
- arm_neon/vmla_n_s32
- arm_neon/vld4_dup_u32
- arm_neon/vshrq_n_s8
- arm_neon/vqaddq_s8
- arm_neon/vshl_n_u64
- arm_neon/vtbl2_p8
- arm_neon/vcleq_u32
- arm_neon/vqsub_u32
- arm_neon/vmovl_u8
- arm_neon/vmlal_u8
- arm_neon/vmul_s8
- armintr/_MoveFromCoprocessor64
- arm_neon/vrsraq_n_s16
- arm_neon/vdupq_n_u32
- arm_neon/vmov_n_s16
- arm_neon/vst4_lane_p8
- arm_neon/vld1_s32
- arm_neon/vst4_p8
- arm_neon/vsriq_n_u32
- arm_neon/vqdmull_n_s16
- arm_neon/vshlq_u32
- arm_neon/vld3_u8
- armintr/_arm_usub16
- arm_neon/vmlsq_lane_s16
- arm_neon/vmovq_n_s8
- arm_neon/int32x4x2_t
- arm_neon/vld4q_u8
- arm_neon/poly16x8x2_t
- arm_neon/vld1q_u64
- arm_neon/vld3q_lane_s16
- arm_neon/int64x1x2_t
- arm_neon/vshlq_n_s8
- arm_neon/vrshl_s64
- arm_neon/vqshl_n_u8
- armintr/_arm_qadd
- armintr/_DSubSatInt
- armintr/_arm_usat16
- arm_neon/vmull_s8
- arm_neon/vsub_s8
- arm_neon/vmovq_n_u16
- arm_neon/vst4_u16
- arm_neon/vmlsl_lane_u32
- arm_neon/vsliq_n_p16
- arm_neon/vmovn_u32
- arm_neon/vbic_u16
- arm_neon/vtbx2_p8
- arm_neon/vrsubhn_s32
- armintr/_SubSatInt
- arm_neon/vst3_u8
- arm_neon/vdupq_n_s32
- arm_neon/vcntq_p8
- arm_neon/vst4_f32
- arm_neon/vbic_s64
- arm_neon/vld3_s64
- arm_neon/vrsra_n_s64
- arm_neon/vqabsq_s16
- arm_neon/vsriq_n_p8
- arm_neon/vst2_lane_p16
- arm_neon/vabsq_s16
- arm_neon/vcombine_u8
- arm_neon/vld2q_p16
- armintr/_CountOneBits
- armintr/__prefetch
- arm_neon/vld3_dup_u64
- arm_neon/vld2q_s16
- arm_neon/vget_low_p16
- arm_neon/vuzpq_u8
- arm_neon/vrev32q_s16
- armintr/_AddSatInt
- arm_neon/uint16x4x2_t
- arm_neon/vmov_n_s32
- arm_neon/vaddl_u16
- arm_neon/vqaddq_s64
- arm_neon/vmlaq_u16
- arm_neon/vsli_n_s8
- armintr/_arm_sxth
- arm_neon/vorr_s32
- arm_neon/vsra_n_u64
- arm_neon/vst2_f16
- arm_neon/vcombine_u16
- arm_neon/vabs_s16
- arm_neon/vsubhn_s32
- arm_neon/vst1q_lane_u32
- arm_neon/vst3_p8
- arm_neon/vqshrun_n_s32
- arm_neon/vcreate_s64
- arm_neon/vld4q_lane_s16
- arm_neon/vzipq_u16
- arm_neon/vmin_s32
- armintr/_CopyInt32FromFloat
- arm_neon/vcgtq_u32
- arm_neon/vabdl_s32
- arm_neon/vqshlq_n_u16
- arm_neon/int8x16x4_t
- arm_neon/vqrdmulh_n_s32
- arm_neon/vqaddq_u64
- arm_neon/vhaddq_s8
- arm_neon/vshll_n_s16
- arm_neon/vuzp_u8
- arm_neon/vaddl_u32
- arm_neon/vld4q_s16
- arm_neon/vqmovun_s16
- arm_neon/vld1q_lane_s8
- arm_neon/vld2_lane_u32
- arm_neon/vrshr_n_s8
- arm_neon/vmlaq_s16
- armintr/_CopyFloatFromInt32
- arm_neon/vmul_f32
- arm_neon/vmlaq_n_f32
- arm_neon/vst4_s16
- arm_neon/vld1_dup_s32
- arm_neon/vmul_u16
- arm_neon/vhaddq_s16
- arm_neon/vst1q_lane_f32
- arm_neon/vrhaddq_u16
- arm_neon/vbicq_u32
- arm_neon/vrev32_s8
- arm_neon/vmlaq_s8
- arm_neon/vmin_s16
- arm_neon/vst3_lane_p16
- arm_neon/vst2q_lane_f32
- arm_neon/vld4q_lane_f32
- arm_neon/vget_low_u16
- arm_neon/vqsub_s32
- arm_neon/vtbl1_s8
- arm_neon/vmovn_s64
- arm_neon/vpmax_s8
- arm_neon/int8x16_t
- arm_neon/vpmin_u8
- arm_neon/vdup_lane_p8
- arm_neon/vsetq_lane_u64
- arm_neon/vuzpq_u16
- arm_neon/vcgeq_u16
- arm_neon/uint8x16x2_t
- armintr/_arm_rev16
- armintr/_arm_sxtb
- arm_neon/vsliq_n_u64
- arm_neon/vmovq_n_u8
- arm_neon/vshlq_n_u32
- arm_neon/vcombine_s64
- armintr/_arm_qsax
- arm_neon/vmin_f32
- armintr/_arm_sadd16
- arm_neon/vmlsq_n_s16
- arm_neon/vorr_u64
- arm_neon/vqrshrun_n_s64
- arm_neon/vld2q_lane_s32
- arm_neon/vgetq_lane_p16
- arm_neon/vrev32_s16
- arm_neon/vqshl_u16
- arm_neon/vtrn_s8
- arm_neon/vst1q_lane_s64
- arm_neon/vtbl4_p8
- arm_neon/vst1_p16
- arm_neon/vmvn_u8
- arm_neon/vld2_lane_u8
- arm_neon/vld2q_u16
- arm_neon/vmovl_s8
- arm_neon/vbslq_u64
- arm_neon/vmls_s8
- arm_neon/vld3q_p16
- arm_neon/vtbl3_u8
- arm_neon/vabs_f32
- arm_neon/vsraq_n_s8
- arm_neon/vqadd_s32
- arm_neon/vmulq_n_s16
- arm_neon/vst3q_s8
- arm_neon/vaddhn_s64
- arm_neon/vmul_n_s16
- arm_neon/vtbl1_p8
- arm_neon/uint64x2x3_t
- arm_neon/vmlsq_s32
- arm_neon/vld2q_lane_u32
- arm_neon/vaddq_u8
- arm_neon/vcombine_f16
- arm_neon/vandq_s16
- arm_neon/vst4q_lane_p16
- arm_neon/vsri_n_u8
- arm_neon/vst3_lane_p8
- arm_neon/vst3_lane_s16
- arm_neon/vdup_n_s16
- arm_neon/vbicq_s8
- arm_neon/vdup_lane_u8
- arm_neon/vst4q_lane_s32
- arm_neon/vqrshl_u16
- arm_neon/vrsra_n_u32
- arm_neon/vdupq_lane_p8
- arm_neon/vld3_lane_u8
- arm_neon/vqrdmulh_n_s16
- arm_neon/vpmin_s32
- armintr/__cps
- arm_neon/vshl_u32
- armintr/_arm_uadd16
- arm_neon/vld3_s16
- arm_neon/vcvt_f32_s32
- arm_neon/vshlq_n_u64
- arm_neon/vrev64q_u8
- arm_neon/vextq_u16
- arm_neon/vsubl_s16
- arm_neon/vget_lane_p8
- arm_neon/vabal_s16
- arm_neon/vrecpeq_u32
- arm_neon/vminq_u8
- arm_neon/veor_s16
- arm_neon/vmull_n_u16
- arm_neon/vshl_n_u8
- arm_neon/vrev32q_u8
- arm_neon/vandq_s8
- arm_neon/vrshlq_s16
- arm_neon/vst4q_p16
- arm_neon/vandq_s32
- armintr/_MoveToCoprocessor2
- arm_neon/vqdmlsl_lane_s32
- arm_neon/vld1q_s64
- arm_neon/vmull_n_s16
- arm_neon/vneg_s16
- arm_neon/vqshluq_n_s64
- arm_neon/vst2_lane_s32
- arm_neon/vmvnq_u16
- arm_neon/vshll_n_s32
- arm_neon/vld3_dup_s8
- arm_neon/vtstq_s32
- arm_neon/vmlsl_u32
- arm_neon/vqdmulhq_lane_s16
- arm_neon/vaddl_s32
- armintr/_CountLeadingZeros
- arm_neon/vqrshrn_n_s16
- arm_neon/vmla_lane_u32
- arm_neon/vst1_u8
- arm_neon/vshl_u64
- arm_neon/vshr_n_u8
- arm_neon/vmull_lane_s32
- arm_neon/vmlal_lane_u32
- arm_neon/vsubl_s8
- arm_neon/float32x2x2_t
- armintr/_arm_bfc
- arm_neon/vaddq_s16
- arm_neon/vmlal_lane_s32
- arm_neon/vpadd_u16
- arm_neon/vst2q_lane_u16
- arm_neon/vld4_s8
- arm_neon/vst1q_s8
- arm_neon/vshrq_n_u64
- arm_neon/vsli_n_u16
- arm_neon/vqrdmulh_lane_s32
- arm_neon/vst4_lane_u16
- arm_neon/vabdq_f32
- arm_neon/vld2_lane_f16
- arm_neon/vqsub_u64
- arm_neon/vsub_f32
- arm_neon/vld1q_s16
- arm_neon/vmaxq_s16
- arm_neon/vcombine_u32
- arm_neon/vrsraq_n_u32
- armintr/_arm_smusdx
- arm_neon/vrev16_s8
- arm_neon/vqdmulh_n_s32
- arm_neon/vmul_s32
- arm_neon/vabdq_s32
- arm_neon/veor_u64
- arm_neon/vmlsl_n_s32
- arm_neon/vsub_s16
- arm_neon/vadd_u16
- arm_neon/vsriq_n_u16
- arm_neon/vmla_u32
- arm_neon/vuzpq_s32
- arm_neon/vst4q_s8
- arm_neon/vaddhn_u32
- arm_neon/vmlaq_lane_f32
- arm_neon/vld3_lane_s8
- arm_neon/vsliq_n_u32
- arm_neon/vqrshlq_s8
- arm_neon/vqdmlal_n_s32
- arm_neon/uint8x16x4_t
- arm_neon/vcgtq_u16
- arm_neon/vandq_u32
- arm_neon/vld4q_lane_u32
- arm_neon/vzip_p16
- arm_neon/vget_low_p8
- armintr/_arm_shadd8
- arm_neon/vmovn_s16
- arm_neon/vcge_u8
- arm_neon/vld2q_f32
- arm_neon/vaba_u32
- armintr/__iso_volatile_store8
- arm_neon/vst2q_p16
- arm_neon/vmul_s16
- arm_neon/vand_s16
- arm_neon/vtbx4_p8
- arm_neon/vceq_u8
- arm_neon/vrhaddq_s16
- arm_neon/vgetq_lane_f32
- arm_neon/vqshl_s8
- arm_neon/vbslq_f32
- arm_neon/vrsqrts_f32
- arm_neon/vld2q_s8
- arm_neon/vtbl1_u8
- arm_neon/vtst_u8
- arm_neon/vrev64q_f32
- arm_neon/vcle_s8
- arm_neon/vsetq_lane_p16
- arm_neon/vcreate_p16
- arm_neon/vabal_s32
- armintr/_arm_smlald
- arm_neon/vmla_f32
- arm_neon/vtbx2_s8
- arm_neon/int64x1x3_t
- arm_neon/vclz_s8
- arm_neon/vorr_s16
- arm_neon/vornq_s64
- arm_neon/vst1q_u64
- arm_neon/vdupq_n_s8
- armintr/_arm_sadd8
- arm_neon/vextq_s32
- armintr/_arm_smuadx
- armintr/_arm_qsub
- arm_neon/vadd_f32
- arm_neon/vrshrq_n_s16
- arm_neon/vqsub_s8
- arm_neon/vld3_f32
- arm_neon/vhadd_s8
- arm_neon/vmull_n_u32
- arm_neon/vdup_n_u64
- arm_neon/vsubw_s32
- armintr/_arm_sxtab
- armintr/_arm_uxtb16
- arm_neon/vmvn_s16
- arm_neon/vst1_lane_s16
- arm_neon/vqrdmulhq_n_s32
- arm_neon/vsriq_n_s32
- arm_neon/poly8x16x2_t
- arm_neon/vadd_u8
- arm_neon/vuzpq_p8
- arm_neon/vst2q_p8
- armintr/__wfi
- arm_neon/vget_high_u16
- arm_neon/vqrshl_u64
- arm_neon/vld1_dup_s64
- arm_neon/vqrshrn_n_s32
- arm_neon/vrshr_n_s64
- arm_neon/vst3_s8
- arm_neon/poly16x4x3_t
- arm_neon/vqrdmulh_lane_s16
- arm_neon/vmvnq_u32
- arm_neon/vqsubq_u32
- arm_neon/vmovq_n_p8
- arm_neon/vtrn_s16
- arm_neon/vld2q_u32
- arm_neon/vqsubq_u16
- arm_neon/vrsqrteq_u32
- arm_neon/vadd_u64
- armintr/_arm_usat
- arm_neon/vcvtq_n_u32_f32
- arm_neon/vaddq_s8
- arm_neon/vrsraq_n_u16
- arm_neon/vqabs_s16
- arm_neon/vsra_n_s8
- arm_neon/vsra_n_s16
- arm_neon/vqshlq_n_u8
- arm_neon/vpadal_s8
- arm_neon/vmlal_n_u16
- armintr/_CopyDoubleFromInt64
- arm_neon/vaddw_u8
- arm_neon/vmulq_n_s32
- arm_neon/vqaddq_s32
- arm_neon/vmla_lane_f32
- arm_neon/vmlaq_lane_s32
- arm_neon/vld1q_dup_u64
- arm_neon/uint16x8_t
- arm_neon/vld2_s32
- arm_neon/vcltq_f32
- arm_neon/vst4q_f32
- arm_neon/vsri_n_u16
- arm_neon/vshlq_s32
- arm_neon/vgetq_lane_u32
- arm_neon/vld1q_dup_f16
- arm_neon/vrev64q_s16
- arm_neon/vrshrq_n_u32
- arm_neon/vld2q_s32
- arm_neon/vcgtq_s8
- arm_neon/vsubhn_u64
- arm_neon/vmls_n_s32
- armintr/_arm_smmlar
- arm_neon/vld3_dup_u8
- arm_neon/vld3q_lane_p16
- arm_neon/vld2_dup_s64
- arm_neon/vqabs_s32
- arm_neon/vqaddq_u8
- arm_neon/vminq_u32
- arm_neon/vpaddl_u16
- arm_neon/vaba_s16
- arm_neon/vmul_u32
- arm_neon/vst1_lane_u16
- arm_neon/vcreate_f32
- arm_neon/vcvt_f16_f32
- arm_neon/vset_lane_s32
- arm_neon/vshl_s8
- arm_neon/vcgt_s16
- arm_neon/vtrn_f32
- arm_neon/vget_high_s64
- arm_neon/vld3_dup_p8
- arm_neon/vcreate_u64
- arm_neon/vext_u64
- arm_neon/vld1q_dup_s16
- arm_neon/vget_lane_s16
- arm_neon/vqdmlal_s16
- arm_neon/vld2_p16
- arm_neon/vld4_u16
- armintr/_arm_smlalbb
- arm_neon/vrev64_u8
- arm_neon/vbslq_s64
- arm_neon/vsubw_u16
- arm_neon/vrsubhn_u32
- arm_neon/vabdq_u8
- arm_neon/vmls_n_u32
- arm_neon/vshr_n_s32
- arm_neon/vmulq_n_u32
- arm_neon/vst3_p16
- arm_neon/vrev32_u16
- arm_neon/int8x8x3_t
- arm_neon/vst2q_lane_u32
- arm_neon/vextq_p16
- arm_neon/vtrnq_f32
- armintr/_arm_smultt
- arm_neon/vqneg_s8
- arm_neon/vmlsq_lane_s32
- arm_neon/vmov_n_p16
- arm_neon/vraddhn_u64
- arm_neon/vrhadd_u32
- arm_neon/vrev64_u32
- arm_neon/vrshrn_n_s32
- arm_neon/vld4q_f32
- arm_neon/vst2_s8
- arm_neon/vrsqrteq_f32
- arm_neon/uint16x4_t
- arm_neon/vget_low_s8
- arm_neon/vst2_lane_u32
- arm_neon/vhsub_s32
- arm_neon/vqdmull_lane_s32
- armintr/_arm_smulwb
- arm_neon/vmlsl_u8
- arm_neon/vdup_lane_s16
- arm_neon/vtbx4_s8
- arm_neon/vld4q_lane_u16
- arm_neon/vget_high_u8
- arm_neon/vclzq_s32
- arm_neon/vld1q_dup_f32
- arm_neon/vtrn_u8
- arm_neon/vqabsq_s8
- arm_neon/vdup_lane_f32
- arm_neon/vqrdmulh_s16
- arm_neon/vst4_u32
- arm_neon/vdup_lane_u32
- arm_neon/vst4_u8
- arm_neon/vmovq_n_s32
- arm_neon/vld2_lane_s8
- arm_neon/vld3_u32
- arm_neon/vsubl_u16
- arm_neon/vqshlu_n_s8
- arm_neon/float32x4_t
- arm_neon/vqshl_n_s32
- arm_neon/float32x2x3_t
- armintr/__hvc
- arm_neon/vst1q_lane_f16
- arm_neon/vmvnq_s16
- arm_neon/vst3q_lane_f32
- arm_neon/vld1q_dup_u8
- arm_neon/vmlsq_s16
- arm_neon/vget_lane_u8
- arm_neon/vld1_lane_s32
- arm_neon/vst4q_s16
- armintr/_arm_qsub8
- arm_neon/vorrq_s32
- arm_neon/vsriq_n_s8
- arm_neon/vqshrn_n_u64
- arm_neon/vdup_n_s32
- armintr/_arm_uhsub8
- arm_neon/vld3_lane_s32
- arm_neon/vbsl_s64
- arm_neon/vld1_dup_f16
- arm_neon/vsli_n_u64
- arm_neon/vraddhn_u32
- arm_neon/vsub_u16
- arm_neon/vcltq_u32
- arm_neon/vminq_f32
- arm_neon/vshl_n_s64
- arm_neon/vld4_u32
- arm_neon/vld1_u32
- arm_neon/vaddhn_u16
- arm_neon/vcvtq_n_f32_s32
- arm_neon/vorn_u64
- arm_neon/vsubhn_u16
- arm_neon/int64x1_t
- arm_neon/vst1q_lane_s8
- arm_neon/vld1q_dup_s32
- arm_neon/vrev32_p8
- arm_neon/vst3q_lane_p16
- arm_neon/vrecpeq_f32
- arm_neon/int8x8x4_t
- arm_neon/vshr_n_u32
- arm_neon/vdupq_lane_s64
- arm_neon/vpaddlq_s8
- arm_neon/vqshl_n_u32
- arm_neon/vmul_u8
- arm_neon/vtbx2_u8
- arm_neon/vshr_n_u64
- arm_neon/vqrshlq_s16
- arm_neon/vst3_lane_u16
- arm_neon/vqsub_u8
- arm_neon/vrsra_n_s16
- arm_neon/vaba_s32
- arm_neon/vsri_n_u64
- arm_neon/vst3q_lane_u32
- arm_neon/vmlsq_n_u32
- arm_neon/poly8x16_t
- arm_neon/vld2_u8
- armintr/_arm_smmulr
- arm_neon/vtst_s16
- armintr/_arm_smmls
- arm_neon/vqdmulh_s16
- arm_neon/vtrnq_u8
- arm_neon/vset_lane_p8
- arm_neon/vmlsl_u16
- arm_neon/vshrn_n_u16
- arm_neon/vld1_dup_p8
- arm_neon/vrev16q_s8
- arm_neon/vmov_n_s8
- arm_neon/vld1_u64
- arm_neon/vpmin_f32
- arm_neon/vmla_n_u16
- arm_neon/vst1_f16
- arm_neon/vqdmlsl_s16
- arm_neon/vmin_u32
- armintr/_arm_qsub16
- arm_neon/vcage_f32
- arm_neon/vornq_u32
- arm_neon/vpadd_s16
- arm_neon/vld1_u8
- arm_neon/vhsubq_s16
- arm_neon/vld1_dup_u32
- arm_neon/vld4_u64
- armintr/_MulHigh
- arm_neon/vmaxq_u8
- arm_neon/vget_lane_u16
- arm_neon/vld2q_u8
- arm_neon/vld1q_dup_p16
- arm_neon/vsraq_n_u8
- arm_neon/vqdmlsl_n_s32
- arm_neon/vst1_s16
- arm_neon/vst1q_s32
- arm_neon/vmaxq_f32
- arm_neon/vqdmulh_lane_s16
- armintr/__isb
- arm_neon/vuzpq_p16
- arm_neon/vmls_lane_s16
- arm_neon/vtbl4_s8
- arm_neon/vst1_lane_p8
- arm_neon/vsubw_s8
- arm_neon/vmin_u8
- arm_neon/vzip_u16
- arm_neon/vld4q_u16
- arm_neon/vshrn_n_s32
- arm_neon/vpadal_u16
- arm_neon/vorrq_s8
- arm_neon/vrshlq_u64
- arm_neon/vst3_lane_s32
- arm_neon/vqshluq_n_s32
- armintr/_arm_shsub16
- arm_neon/vst1_u32
- arm_neon/vrhadd_s16
- arm_neon/vzipq_s32
- arm_neon/vshrq_n_u16
- arm_neon/vcls_s32
- arm_neon/vceq_s8
- arm_neon/vld2q_lane_f16
- arm_neon/vst4q_u8
- arm_neon/vraddhn_u16
- arm_neon/vget_lane_u64
- armintr/_arm_smlsld
- arm_neon/vld3_u64
- arm_neon/vld1_lane_s16
- arm_neon/vabd_f32
- arm_neon/vdupq_n_u16
- armintr/__iso_volatile_store64
- arm_neon/vqsubq_u8
- arm_neon/poly16x8x3_t
- arm_neon/vcltq_s32
- arm_neon/vqnegq_s16
- arm_neon/vqsub_u16
- arm_neon/vaddq_s32
- arm_neon/vqshl_n_s64
- arm_neon/vabdl_s8
- arm_neon/vclsq_s16
- arm_neon/vpaddl_u8
- arm_neon/vmlsq_n_u16
- armintr/_arm_uqadd8
- arm_neon/vhsub_u32
- arm_neon/vset_lane_s16
- arm_neon/vsubl_u32
- arm_neon/vld3_lane_f32
- arm_neon/vcle_s16
- arm_neon/vmovl_u32
- arm_neon/vst3_lane_f16
- arm_neon/vcaltq_f32
- arm_neon/vsubq_s32
- arm_neon/vand_s64
- arm_neon/vst2_u8
- arm_neon/vcombine_p8
- arm_neon/vqdmlal_s32
- arm_neon/vsub_s32
- armintr/_arm_uxtab16
- arm_neon/vmlsq_n_f32
- armintr/_arm_qdsub
- arm_neon/vhaddq_u32
- arm_neon/vhsubq_u16
- arm_neon/vmlsq_lane_u16
- arm_neon/vst4_s64
- armintr/_CountLeadingOnes
- armintr/_arm_smlabt
- arm_neon/vcombine_s32
- arm_neon/vld4_lane_f16
- arm_neon/vadd_s64
- arm_neon/vorrq_u32
- armintr/__sev
- arm_neon/vdupq_lane_s32
- arm_neon/vrecpsq_f32
- arm_neon/vbicq_u16
- arm_neon/vld1_lane_p16
- arm_neon/vrshr_n_u32
- arm_neon/vcgeq_s32
- arm_neon/vld4_dup_s16
- arm_neon/vld1q_p8
- arm_neon/vrshlq_u16
- arm_neon/vmlaq_lane_u32
- arm_neon/vsub_s64
- arm_neon/vcreate_u16
- arm_neon/vget_lane_s32
- arm_neon/vuzp_f32
- arm_neon/vld2_lane_p8
- arm_neon/vuzp_u16
- arm_neon/vorrq_s16
- armintr/_arm_smlaltb
- arm_neon/vrshrn_n_s16
- arm_neon/vabd_s8
- arm_neon/vnegq_s8
- arm_neon/vst4q_u16
- arm_neon/vst1q_lane_s32
- arm_neon/vst1_lane_s32
- arm_neon/vmla_u16
- arm_neon/vmls_lane_s32
- arm_neon/vtst_s8
- arm_neon/vcgeq_s8
- arm_neon/poly8x8x4_t
- arm_neon/vqsub_s64
- armintr/_arm_uqasx
- arm_neon/vld1_lane_u64
- arm_neon/vminq_s16
- arm_neon/vmulq_u32
- arm_neon/vqrshlq_u8
- arm_neon/vdupq_n_p16
- arm_neon/vld4_dup_f16
- arm_neon/vcls_s16
- arm_neon/vmov_n_u64
- arm_neon/vmla_s32
- arm_neon/vrshl_s16
- arm_neon/vcalt_f32
- arm_neon/int64x2x3_t
- arm_neon/vsub_u8
- arm_neon/vzipq_u8
- arm_neon/vrshrn_n_u64
- arm_neon/vrshlq_s32
- arm_neon/vorr_s64
- arm_neon/vqrshl_s16
- arm_neon/vceqq_u16
- arm_neon/vmulq_n_u16
- arm_neon/vmlaq_u8
- arm_neon/vsri_n_s64
- arm_neon/vld3q_u8
- arm_neon/vld1_dup_s16
- arm_neon/vld1q_s32
- arm_neon/vsri_n_s16
- arm_neon/vshlq_u8
- arm_neon/vsli_n_s64
- arm_neon/vmull_lane_u32
- arm_neon/vshl_s64
- arm_neon/vcreate_s16
- arm_neon/uint8x8x4_t
- arm_neon/vqshrn_n_s32
- arm_neon/vqshlq_u32
- arm_neon/vmlal_n_u32
- arm_neon/vtrnq_s16
- arm_neon/vshr_n_s64
- arm_neon/vst2_u16
- arm_neon/vtrn_s32
- arm_neon/vsubhn_u32
- arm_neon/vbicq_s16
- arm_neon/vsetq_lane_s8
- arm_neon/vrsubhn_s16
- arm_neon/vhsub_u8
- arm_neon/vcleq_s32
- arm_neon/vld4_dup_s8
- arm_neon/vmull_u32
- arm_neon/vrshr_n_s16
- arm_neon/vst1q_lane_s16
- arm_neon/vmlsq_lane_u32
- arm_neon/vnegq_f32
- arm_neon/vmin_s8
- arm_neon/vrev16_p8
- arm_neon/vbic_u8
- arm_neon/vclzq_u16
- arm_neon/vcge_u32
- arm_neon/vget_high_u64
- arm_neon/vabsq_s8
- arm_neon/vhaddq_u16
- arm_neon/vsraq_n_s64
- arm_neon/vld2_u32
- arm_neon/vld2_lane_f32
- arm_neon/vqrshrn_n_u32
- arm_neon/vbslq_s8
- armintr/_CountLeadingZeros64
- arm_neon/vbicq_u8
- arm_neon/vdup_lane_s8
- arm_neon/vpadd_s32
- arm_neon/vld3q_lane_f16
- arm_neon/vaba_u8
- arm_neon/vqshlq_u16
- arm_neon/vst1q_u8
- arm_neon/vst4q_lane_f16
- arm_neon/vshl_n_u16
- armintr/_arm_smladx
- arm_neon/vmla_lane_s16
- arm_neon/vornq_u8
- arm_neon/vqneg_s32
- arm_neon/vadd_s8
- arm_neon/vcle_u32
- arm_neon/vclzq_u8
- arm_neon/vtbx1_u8
- armintr/_CountLeadingOnes64
- armintr/__dsb
- arm_neon/vaddq_u32
- arm_neon/vclsq_s8
- arm_neon/vdup_n_s64
- arm_neon/vmax_s16
- arm_neon/vst2q_u32
- arm_neon/vsetq_lane_s64
- arm_neon/vtst_p8
- arm_neon/vabs_s8
- arm_neon/vqshl_n_s16
- arm_neon/vqrshrn_n_u64
- arm_neon/vaddw_s8
- armintr/_arm_uhadd16
- arm_neon/vsriq_n_p16
- arm_neon/vld4_lane_u32
- arm_neon/vneg_f32
- armintr/_MoveToCoprocessor
- arm_neon/vmvnq_s8
- arm_neon/vld1q_lane_p8
- arm_neon/uint32x2x3_t
- arm_neon/vrshrn_n_u16
- arm_neon/vld3_f16
- arm_neon/vsriq_n_s16
- arm_neon/vshlq_n_s16
- arm_neon/vabal_u8
- arm_neon/vqshluq_n_s16
- arm_neon/vst2_lane_u16
- arm_neon/vbic_s16
- arm_neon/vqshl_n_u64
- arm_neon/vcagt_f32
- arm_neon/vpadalq_s8
- arm_neon/vclz_s32
- arm_neon/vld1_lane_s64
- arm_neon/vget_high_p8
- arm_neon/uint64x1_t
- arm_neon/vextq_s16
- arm_neon/vpadd_s8
- arm_neon/vrsubhn_u64
- arm_neon/vst3q_f16
- arm_neon/vdupq_lane_u16
- arm_neon/vrshrq_n_u64
- arm_neon/vmovq_n_f32
- arm_neon/vld1q_dup_u16
- arm_neon/vshr_n_u16
- arm_neon/uint32x2_t
- armintr/_arm_umull
- arm_neon/vtrnq_u16
- arm_neon/vsetq_lane_u32
- arm_neon/vneg_s8
- arm_neon/vsetq_lane_u8
- arm_neon/vst2q_lane_s16
- arm_neon/vqmovun_s32
- armintr/_arm_usad8
- armintr/_arm_pkhbt
- arm_neon/uint16x4x3_t
- arm_neon/vsra_n_s32
- arm_neon/vqmovun_s64
- arm_neon/vld1q_dup_s8
- arm_neon/vaddhn_s32
- arm_neon/vpmax_f32
- arm_neon/vpadd_u32
- arm_neon/vhsubq_u32
- arm_neon/vqrshrun_n_s32
- arm_neon/vadd_s32
- arm_neon/vclt_s8
- arm_neon/vorrq_s64
- arm_neon/vst4q_f16
- arm_neon/vst1_s32
- arm_neon/vceq_p8
- arm_neon/vsubw_s16
- arm_neon/vgetq_lane_u64
- arm_neon/vmla_n_u32
- arm_neon/vcvtq_f32_s32
- arm_neon/vld1q_u32
- arm_neon/vmax_f32
- armintr/_isunorderedf
- arm_neon/vrshl_u8
- arm_neon/vld4_dup_s64
- arm_neon/vqaddq_u16
- arm_neon/vld4q_lane_f16
- arm_neon/vceqq_p8
- arm_neon/vsubw_u8
- arm_neon/vqmovn_u16
- armintr/_arm_smlsldx
- arm_neon/vcreate_p8
- arm_neon/vqdmull_n_s32
- arm_neon/uint64x2_t
- arm_neon/vmls_s32
- arm_neon/vst3q_f32
- armintr/_arm_bfi
- armintr/_arm_qadd16
- arm_neon/vrshlq_s8
- arm_neon/vget_lane_p16
- arm_neon/vld2_p8
- arm_neon/vld3_lane_u32
- armintr/_MoveFromCoprocessor2
- arm_neon/vqshl_u8
- arm_neon/poly8_t
- arm_neon/vhadd_u16
- arm_neon/vmla_lane_u16
- arm_neon/vshrq_n_u8
- arm_neon/vuzpq_f32
- arm_neon/vmls_lane_f32
- arm_neon/vqneg_s16
- arm_neon/vtrn_p16
- arm_neon/vshrn_n_u32
- arm_neon/vaddhn_u64
- arm_neon/vabal_u32
- arm_neon/vld1q_lane_u32
- arm_neon/vrsraq_n_s32
- arm_neon/vandq_u64
- arm_neon/vqdmull_s32
- arm_neon/vext_s16
- arm_neon/vaddw_s16
- arm_neon/vrev64q_p8
- arm_neon/uint8x8x3_t
- arm_neon/vzip_f32
- armintr/_arm_ssub8
- arm_neon/uint16x4x4_t
- armintr/__swi
- armintr/_arm_smlatb
- arm_neon/vrhaddq_s8
- arm_neon/vpmax_s32
- arm_neon/vqshl_s64
- arm_neon/vrev16q_p8
- arm_neon/vqmovn_u32
- arm_neon/vld1q_f16
- arm_neon/vornq_u64
- arm_neon/vqshlq_n_s16
- arm_neon/vld1_f16
- armintr/_arm_smmlsr
- arm_neon/vshlq_s16
- arm_neon/vsubhn_s16
- arm_neon/vmulq_p8
- arm_neon/vdupq_lane_f32
- armintr/_arm_shadd16
- arm_neon/vornq_s16
- arm_neon/vst1q_lane_u8
- arm_neon/vcaleq_f32
- arm_neon/vst3q_lane_f16
- armintr/_arm_sdiv
- arm_neon/vld2_u16
- arm_neon/vdup_lane_u16
- arm_neon/vst4q_lane_f32
- arm_neon/vdup_n_f32
- arm_neon/vsubq_u8
- arm_neon/vset_lane_p16
- arm_neon/vrsqrte_f32
- arm_neon/vsubl_u8
- arm_neon/vld3q_lane_f32
- arm_neon/vqnegq_s8
- arm_neon/vqmovn_s16
- arm_neon/int16x8x3_t
- arm_neon/veorq_u16
- arm_neon/vqdmulh_n_s16
- arm_neon/vhaddq_u8
- arm_neon/vpadal_u8
- arm_neon/vst2q_s16
- arm_neon/poly16x8x4_t
- arm_neon/int64x2_t
- arm_neon/vmull_s32
- arm_neon/vld4_lane_s32
- arm_neon/vst4q_p8
- arm_neon/vmlal_lane_u16
- arm_neon/vclz_u32
- arm_neon/vsliq_n_s8
- arm_neon/vmls_n_f32
- arm_neon/vmlsl_lane_s16
- arm_neon/vst4q_u32
- arm_neon/vld1q_lane_s16
- arm_neon/vst1q_f32
- arm_neon/vrshr_n_u8
- arm_neon/vst1q_s64
- arm_neon/vbslq_u32
- arm_neon/vset_lane_s8
- arm_neon/vdupq_lane_p16
- arm_neon/vtstq_s16
- arm_neon/vshl_n_s8
- arm_neon/vqrdmulhq_n_s16
- arm_neon/vget_high_f16
- arm_neon/vst4_lane_u32
- arm_neon/vraddhn_s16
- arm_neon/vmlsl_lane_s32
- arm_neon/vld3q_s32
- arm_neon/vsriq_n_u64
- arm_neon/vld4_dup_u8
- arm_neon/vld4q_s8
- arm_neon/vqmovn_s64
- arm_neon/vrev32q_p8
- arm_neon/vsliq_n_p8
- arm_neon/vzipq_s16
- arm_neon/vgetq_lane_s64
- arm_neon/vst4_p16
- arm_neon/vsubq_u16
- arm_neon/vrev64_s32
- armintr/_arm_uhadd8
- arm_neon/vornq_u16
- arm_neon/vst4_lane_s8
- arm_neon/vabd_s32
- arm_neon/vqrdmulhq_s16
- arm_neon/vqshlq_s32
- arm_neon/int64x2x4_t
- arm_neon/vset_lane_u16
- arm_neon/vrsra_n_s32
- arm_neon/vabdl_u16
- arm_neon/vsliq_n_s32
helpviewer_keywords:
- cl.exe compiler, intrinsics
- intrinsics, ARM
ms.assetid: d3d7dadd-7bd5-4508-8bff-371a66913e20
ms.openlocfilehash: 7a6020b4333c11f5581742e85ea16ce9c43e9dca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368218"
---
# <a name="arm-intrinsics"></a>Funkcje wewnętrzne ARM

Kompilator Microsoft C++ (MSVC) udostępnia następujące elementy wewnętrzne w architekturze ARM. Aby uzyskać więcej informacji na temat usługi ARM, zobacz sekcje Architektury i narzędzi programistycznych w [witrynie ARM Developer Documentation](https://developer.arm.com/docs) w sieci Web.

## <a name="neon"></a><a name="top"></a>Neon

Rozszerzenia zestawu instrukcji wektorowych NEON dla arm zapewniają funkcje pojedynczej instrukcji wielokrotnego przesyłania danych (SIMD), które przypominają te w zestawach instrukcji wektorowych MMX i SSE, które są wspólne dla procesorów architektury x86 i x64.

Neon intrinsics są obsługiwane, jak podano `arm_neon.h`w pliku nagłówka . Obsługa msvc dla neonu wewnętrznego przypomina to z kompilatora ARM, który jest udokumentowany w dodatku G [z arm kompilatora toolchain, wersja 4.1 Odwołanie kompilatora](https://go.microsoft.com/fwlink/p/?LinkId=251083) w witrynie ARM Infocenter.

Podstawową różnicą między kompilatorem MSVC a `_ex` arm jest `vldX` `vstX` to, że MSVC dodaje warianty obciążenia wektorowego i instrukcji przechowywania. Warianty `_ex` przyjmują dodatkowy parametr, który określa wyrównanie argumentu wskaźnika,`_ex` ale w przeciwnym razie są identyczne z ich odpowiednikami niezwiązanym z tym.

## <a name="arm-specific-intrinsics-listing"></a><a name="A"></a>Lista wewnętrznych specyficznych dla ARM

|Nazwa funkcji|Instrukcja|Prototyp funkcji|
|-------------------|-----------------|------------------------|
|_arm_smlal|SMLAL (SMLAL)|__int64 _arm_smlal(\__int64 _RdHiLo, int _Rn, int _Rm)|
|_arm_umlal|UMLAL (UMLAL)|_arm_umlal __int64 bez podpisu (_RdHiLo \__int64 bez podpisu, niepodpisane _Rn int, niepodpisane _Rm int)|
|_arm_clz|Clz|unsigned int _arm_clz (niepodpisane int _Rm)|
|_arm_qadd|Funkcja QADD|int _arm_qadd (int _Rm, int _Rn)|
|_arm_qdadd|QDADD ( QDADD )|int _arm_qdadd(int _Rm, int _Rn)|
|_arm_qdsub|Z O.O.|int _arm_qdsub(int _Rm, int _Rn)|
|_arm_qsub|funkcja QSUB|int _arm_qsub(int _Rm, int _Rn)|
|_arm_smlabb|SMLABB (WŁAZ SMLABB)|int _arm_smlabb(int _Rn, int _Rm, int _Ra)|
|_arm_smlabt|SMLABT ( SMLABT )|int _arm_smlabt(int _Rn, int _Rm, int _Ra)|
|_arm_smlatb|SMLATB ( SMLATB )|int _arm_smlatb(int _Rn, int _Rm, int _Ra)|
|_arm_smlatt|SMLATT ( SMLATT )|int _arm_smlatt(int _Rn, int _Rm, int _Ra)|
|_arm_smlalbb|SMLALBB ( SMLALBB )|__int64 _arm_smlalbb(\__int64 _RdHiLo, int _Rn, int _Rm)|
|_arm_smlalbt|SMLALBT (SMLALBT)|__int64 _arm_smlalbt(\__int64 _RdHiLo, int _Rn, int _Rm)|
|_arm_smlaltb|SMLALTB ( SMLALTB )|__int64 _arm_smlaltb(\__int64 _RdHiLo, int _Rn _Rm, int _Rm)|
|_arm_smlaltt|SMLALTT ( SMLALTT )|__int64 _arm_smlaltt(\__int64 _RdHiLo, int _Rn, int _Rm)|
|_arm_smlawb|SMLAWB (WŁASJA)|int _arm_smlawb(int _Rn, int _Rm, int _Ra)|
|_arm_smlawt|SMLAWT ( SMLAWT )|int _arm_smlawt(int _Rn, int _Rm, int _Ra)|
|_arm_smulbb|SMULBB ( SMULBB )|int _arm_smulbb(int _Rn, int _Rm)|
|_arm_smulbt|SMULBT ( SMULBT )|int _arm_smulbt (int _Rn, int _Rm)|
|_arm_smultb|SMULTB ( SMULTB )|int _arm_smultb(int _Rn, int _Rm)|
|_arm_smultt|SMULTT (WŁAZ SMULTT)|int _arm_smultt (int _Rn, int _Rm)|
|_arm_smulwb|SMULWB ( SMULWB )|int _arm_smulwb(int _Rn, int _Rm)|
|_arm_smulwt|SMULWT ( SMULWT )|int _arm_smulwt(int _Rn, int _Rm)|
|_arm_sadd16|16 000 000 00|int _arm_sadd16(int _Rn, int _Rm)|
|_arm_sadd8|SADD8 (800 zł)|int _arm_sadd8 (int _Rn, int _Rm)|
|_arm_sasx|SASX ( SASX )|int _arm_sasx(int _Rn, int _Rm)|
|_arm_ssax|SSAX (SSAX)|int _arm_ssax (int _Rn, int _Rm)|
|_arm_ssub16|SSUB16|int _arm_ssub16(int _Rn, int _Rm)|
|_arm_ssub8|ZSUB8|int _arm_ssub8 (int _Rn, int _Rm)|
|_arm_shadd16|ZACIEŃC16|int _arm_shadd16(int _Rn, int _Rm)|
|_arm_shadd8|ZACIEŃC 8|int _arm_shadd8(int _Rn, int _Rm)|
|_arm_shasx|SHASX ( SHASX )|int _arm_shasx(int _Rn, int _Rm)|
|_arm_shsax|OKRĘG WYBORCZY SHSAX|int _arm_shsax (int _Rn, int _Rm)|
|_arm_shsub16|ShsUB16 (właśc.|int _arm_shsub16(int _Rn, int _Rm)|
|_arm_shsub8|Shsub8 ( SHSUB8 )|int _arm_shsub8 (int _Rn, int _Rm)|
|_arm_qadd16|QADD16|int _arm_qadd16 (int _Rn, int _Rm)|
|_arm_qadd8|QADD8 ( QADD8 )|int _arm_qadd8(int _Rn, int _Rm)|
|_arm_qasx|Okręg wyborczy QASX|int _arm_qasx(int _Rn, int _Rm)|
|_arm_qsax|QSAX ( QSAX )|int _arm_qsax(int _Rn, int _Rm)|
|_arm_qsub16|QSUB16|int _arm_qsub16 (int _Rn, int _Rm)|
|_arm_qsub8|QSUB8 ( QSUB8 )|int _arm_qsub8 (int _Rn, int _Rm)|
|_arm_uadd16|UADD16|unsigned int _arm_uadd16(unsigned int _Rn, unsigned int _Rm)|
|_arm_uadd8|UADD8 ( UADD8 )|unsigned int _arm_uadd8(unsigned int _Rn, unsigned int _Rm)|
|_arm_uasx|UASX (uasx)|unsigned int _arm_uasx(unsigned int _Rn, unsigned int _Rm)|
|_arm_usax|UsaX ( USAX )|unsigned int _arm_usax (niepodpisane int _Rn, niepodpisane int _Rm)|
|_arm_usub16|16 usub16|unsigned int _arm_usub16(unsigned int _Rn, unsigned int _Rm)|
|_arm_usub8|U.|unsigned int _arm_usub8(unsigned int _Rn, unsigned int _Rm)|
|_arm_uhadd16|UHADD16 ( UHADD16 )|unsigned int _arm_uhadd16(unsigned int _Rn, unsigned int _Rm)|
|_arm_uhadd8|UHADD8 (polski)|unsigned int _arm_uhadd8 (niepodpisane int _Rn, niepodpisane int _Rm)|
|_arm_uhasx|UHASX ( UHASX )|unsigned int _arm_uhasx (niepodpisane int _Rn, niepodpisane int _Rm)|
|_arm_uhsax|ZOSAX|unsigned int _arm_uhsax (niepodpisane int _Rn, niepodpisane int _Rm)|
|_arm_uhsub16|UHSUB16|unsigned int _arm_uhsub16(unsigned int _Rn, unsigned int _Rm)|
|_arm_uhsub8|UHSUB8|unsigned int _arm_uhsub8 (niepodpisane int _Rn, niepodpisane int _Rm)|
|_arm_uqadd16|UQADD16|unsigned int _arm_uqadd16(unsigned int _Rn, unsigned int _Rm)|
|_arm_uqadd8|UQADD8 ( UQADD8 )|unsigned int _arm_uqadd8 (niepodpisane int _Rn, niepodpisane int _Rm)|
|_arm_uqasx|UQASX ( UQASX )|unsigned int _arm_uqasx(unsigned int _Rn, unsigned int _Rm)|
|_arm_uqsax|UQSAX ( UQSAX )|unsigned int _arm_uqsax(unsigned int _Rn, unsigned int _Rm)|
|_arm_uqsub16|UQSUB16|unsigned int _arm_uqsub16 (niepodpisane int _Rn, niepodpisane int _Rm)|
|_arm_uqsub8|UQSUB8 (WYD.|unsigned int _arm_uqsub8(unsigned int _Rn, unsigned int _Rm)|
|_arm_sxtab|SXTAB ( SXTAB )|int _arm_sxtab(int _Rn, int _Rm, niepodpisany int _Rotation)|
|_arm_sxtab16|SXTAB16 (WYCHYNAST)|int _arm_sxtab16 (int _Rn, int _Rm, niepodpisane int _Rotation)|
|_arm_sxtah|SXTAH ( SXTAH )|int _arm_sxtah (int _Rn, int _Rm, niepodpisane int _Rotation)|
|_arm_uxtab|UXTAB (polski)|unsigned int _arm_uxtab(unsigned int _Rn, unsigned int _Rm, unsigned int _Rotation)|
|_arm_uxtab16|UXTAB16 (polski)|unsigned int _arm_uxta16b(unsigned int _Rn, unsigned int _Rm, unsigned int _Rotation)|
|_arm_uxtah|UXTAH ( UXTAH )|unsigned int _arm_uxtah(unsigned int _Rn, unsigned int _Rm, unsigned int _Rotation)|
|_arm_sxtb|SXTB ( SXTB )|int _arm_sxtb (int _Rn, niepodpisane int _Rotation)|
|_arm_sxtb16|SXTB16|int _arm_sxtb16 (int _Rn, niepodpisany int _Rotation)|
|_arm_sxth|SXTH (WSK)|int _arm_sxth (int _Rn, niepodpisane int _Rotation)|
|_arm_uxtb|UXTB (polski)|unsigned int _arm_uxtb (niepodpisane int _Rn, niepodpisane int _Rotation)|
|_arm_uxtb16|UXTB16|unsigned int _arm_uxtb16(unsigned int _Rn, unsigned int _Rotation)|
|_arm_uxth|UXTH ( UXTH )|unsigned int _arm_uxth(unsigned int _Rn, unsigned int _Rotation)|
|_arm_pkhbt|PKHBT ( PKHBT )|int _arm_pkhbt (int _Rn, int _Rm, niepodpisane int _Lsl_imm)|
|_arm_pkhtb|PKHTB|int _arm_pkhtb(int _Rn, int _Rm, niepodpisany int _Asr_imm)|
|_arm_usad8|Stany Zjednoczone Ameryki|unsigned int _arm_usad8 (niepodpisane int _Rn, niepodpisane int _Rm)|
|_arm_usada8|USADA8 (USADA8)|unsigned int _arm_usada8(unsigned int _Rn, unsigned int _Rm, unsigned int _Ra)|
|_arm_ssat|SSAT (SSAT)|int _arm_ssat(niepodpisane int _Sat_imm, _int _Rn, _ARMINTR_SHIFT_T _Shift_type, niepodpisane _Shift_imm int)|
|_arm_usat|z o.o.|int _arm_usat(niepodpisane int _Sat_imm, _int _Rn, _ARMINTR_SHIFT_T _Shift_type, niepodpisane _Shift_imm int)|
|_arm_ssat16|SSAT16 (WSAT16)|int _arm_ssat16 (niepodpisany int _Sat_imm, _int _Rn)|
|_arm_usat16|Stany Zjednoczone Ameryki 16|int _arm_usat16 (niepodpisany int _Sat_imm, _int _Rn)|
|_arm_rev|Rev|unsigned int _arm_rev (niepodpisane int _Rm)|
|_arm_rev16|REV16|unsigned int _arm_rev16 (niepodpisane int _Rm)|
|_arm_revsh|REVSH (WYCHYNAS|unsigned int _arm_revsh (niepodpisane int _Rm)|
|_arm_smlad|SMLAD (właswoić)|int _arm_smlad(int _Rn, int _Rm, int _Ra)|
|_arm_smladx|Zsmladowy|int _arm_smladx(int _Rn, int _Rm, int _Ra)|
|_arm_smlsd|SMLSD ( SMLSD )|int _arm_smlsd(int _Rn, int _Rm, int _Ra)|
|_arm_smlsdx|SMLSDX ( SMLSDX )|int _arm_smlsdx(int _Rn, int _Rm, int _Ra)|
|_arm_smmla|SMMLA|int _arm_smmla(int _Rn, int _Rm, int _Ra)|
|_arm_smmlar|SMMLAR ( SMMLAR )|int _arm_smmlar(int _Rn, int _Rm, int _Ra)|
|_arm_smmls|SMMLS (SMMLS)|int _arm_smmls(int _Rn, int _Rm, int _Ra)|
|_arm_smmlsr|SMMLSR ( SMMLSR )|int _arm_smmlsr(int _Rn, int _Rm, int _Ra)|
|_arm_smmul|ZWZ|int _arm_smmul (int _Rn, int _Rm)|
|_arm_smmulr|ZWĘŻACZ|int _arm_smmulr (int _Rn, int _Rm)|
|_arm_smlald|SMLALD (SMLALD)|__int64 _arm_smlald(\__int64 _RdHiLo, int _Rn, int _Rm)|
|_arm_smlaldx|Zsm.|__int64 _arm_smlaldx(\__int64 _RdHiLo, int _Rn, int _Rm)|
|_arm_smlsld|SMLSLD (SMLSLD)|__int64 _arm_smlsld(\__int64 _RdHiLo, int _Rn, int _Rm)|
|_arm_smlsldx|SMLSLDX ( SMLSLDX )|__int64 _arm_smlsldx(\__int64 _RdHiLo, int _Rn, int _Rm)|
|_arm_smuad|SMUAD ( SMUAD )|int _arm_smuad (int _Rn, int _Rm)|
|_arm_smuadx|SMUADX ( SMUADX )|int _arm_muadxs(int _Rn, int _Rm)|
|_arm_smusd|SMUSD (smusd)|int _arm_smusd (int _Rn, int _Rm)|
|_arm_smusdx|SMUSDX ( SMUSDX )|int _arm_smusdx(int _Rn, int _Rm)|
|_arm_smull|SMULL ( SMULL )|__int64 _arm_smull (int _Rn, int _Rm)|
|_arm_umull|UMULL ( UMULL )|niepodpisane __int64 _arm_umull (niepodpisane _Rn int, niepodpisane _Rm int)|
|_arm_umaal|UMAAL (UMAAL)|niepodpisane __int64 _arm_umaal (niepodpisane int _RdLo, niepodpisane int _RdHi, niepodpisane int _Rn, niepodpisane int _Rm)|
|_arm_bfc|Bfc|unsigned int _arm_bfc(unsigned int _Rd, unsigned int _Lsb, unsigned int _Width)|
|_arm_bfi|Bfi|unsigned int _arm_bfi(unsigned int _Rd, unsigned int _Rn, unsigned int _Lsb, unsigned int _Width)|
|_arm_rbit|RBIT|unsigned int _arm_rbit (niepodpisane int _Rm)|
|_arm_sbfx|SBFX ( SBFX )|int _arm_sbfx (int _Rn, niepodpisane int _Lsb, niepodpisane int _Width)|
|_arm_ubfx|UBFX (polski)|unsigned int _arm_ubfx(unsigned int _Rn, unsigned int _Lsb, unsigned int _Width)|
|_arm_sdiv|SDIV (SDIV)|int _arm_sdiv(int _Rn, int _Rm)|
|_arm_udiv|UDIV (UDIV)|unsigned int _arm_udiv(unsigned int _Rn, unsigned int _Rm)|
|__cps|Cps|void __cps (niepodpisane int _Ops, niepodpisane int _Flags, niepodpisane int _Mode)|
|__dmb|Dmb|void __dmb(unsigned int) `_Type`<br /><br /> Wstawia operację bariery pamięci do strumienia instrukcji. Parametr `_Type` określa rodzaj ograniczenia, który wymusza barierę.<br /><br /> Aby uzyskać więcej informacji na temat rodzajów ograniczeń, które mogą być wymuszane, zobacz [Ograniczenia barier pamięci](#BarrierRestrictions).|
|__dsb|Dsb|void __dsb (niepodpisane int _Type)<br /><br /> Wstawia operację bariery pamięci do strumienia instrukcji. Parametr `_Type` określa rodzaj ograniczenia, który wymusza barierę.<br /><br /> Aby uzyskać więcej informacji na temat rodzajów ograniczeń, które mogą być wymuszane, zobacz [Ograniczenia barier pamięci](#BarrierRestrictions).|
|__isb|Isb|void __isb (niepodpisane int _Type)<br /><br /> Wstawia operację bariery pamięci do strumienia instrukcji. Parametr `_Type` określa rodzaj ograniczenia, który wymusza barierę.<br /><br /> Aby uzyskać więcej informacji na temat rodzajów ograniczeń, które mogą być wymuszane, zobacz [Ograniczenia barier pamięci](#BarrierRestrictions).|
|__emit||void __emit (niepodpisany \_kod opcode _int32)<br /><br /> Wstawia określoną instrukcję do strumienia instrukcji, który jest odtwarzany przez kompilator.<br /><br /> Wartość `opcode` musi być wyrażeniem stałym, które jest znane w czasie kompilacji. Rozmiar słowa instrukcji wynosi 16 bitów, a najważniejsze 16 bitów `opcode` jest ignorowanych.<br /><br /> Kompilator nie podejmuje żadnej próby `opcode` interpretacji zawartości i nie gwarantuje stan procesora CPU lub pamięci przed wykonaniem wstawionej instrukcji.<br /><br /> Kompilator zakłada, że stany procesora CPU i pamięci pozostają niezmienione po wykonaniu wstawionej instrukcji. W związku z tym instrukcje, które zmieniają stan może mieć szkodliwy wpływ na normalny kod, który jest generowany przez kompilator.<br /><br /> Z tego powodu `emit` należy używać tylko do wstawiania instrukcji, które wpływają na stan procesora CPU, które zwykle nie przetwarza kompilator — na przykład stanu koprocenzera — lub implementacji funkcji, które są zadeklarowane za pomocą . `declspec(naked)`|
|__hvc|Hvc|unsigned int __hvc(unsigned int, ...)|
|__iso_volatile_load16||__int16 \__iso_volatile_load16 (const volatile \_ \*_int16)<br /><br /> Aby uzyskać więcej informacji, zobacz [__iso_volatile_load/magazynu wewnętrznego](#IsoVolatileLoadStore).|
|__iso_volatile_load32||__int32 \__iso_volatile_load32(const volatile \_ \*_int32)<br /><br /> Aby uzyskać więcej informacji, zobacz [__iso_volatile_load/magazynu wewnętrznego](#IsoVolatileLoadStore).|
|__iso_volatile_load64||__int64 \__iso_volatile_load64 (const volatile \_ \*_int64)<br /><br /> Aby uzyskać więcej informacji, zobacz [__iso_volatile_load/magazynu wewnętrznego](#IsoVolatileLoadStore).|
|__iso_volatile_load8||__int8 \__iso_volatile_load8 (const volatile \_ \*_int8)<br /><br /> Aby uzyskać więcej informacji, zobacz [__iso_volatile_load/magazynu wewnętrznego](#IsoVolatileLoadStore).|
|__iso_volatile_store16||void __iso_volatile_store16(lotny \__int16 \*, \__int16)<br /><br /> Aby uzyskać więcej informacji, zobacz [__iso_volatile_load/magazynu wewnętrznego](#IsoVolatileLoadStore).|
|__iso_volatile_store32||void __iso_volatile_store32(lotny \__int32 \*, \__int32)<br /><br /> Aby uzyskać więcej informacji, zobacz [__iso_volatile_load/magazynu wewnętrznego](#IsoVolatileLoadStore).|
|__iso_volatile_store64||void __iso_volatile_store64(lotny \__int64 \*, \__int64)<br /><br /> Aby uzyskać więcej informacji, zobacz [__iso_volatile_load/magazynu wewnętrznego](#IsoVolatileLoadStore).|
|__iso_volatile_store8||void __iso_volatile_store8(lotny \__int8 \*, \__int8)<br /><br /> Aby uzyskać więcej informacji, zobacz [__iso_volatile_load/magazynu wewnętrznego](#IsoVolatileLoadStore).|
|__ldrexd|LDREXD ( LDREXD )|__int64 \__ldrexd(const volatile \_ \*_int64)|
|__prefetch|Pld|void __cdecl \__prefetch(const void) \*<br /><br /> Zawiera `PLD` wskazówkę pamięci do systemu, że pamięć na lub w pobliżu określonego adresu mogą być dostępne wkrótce. Niektóre systemy mogą zoptymalizować dla tego wzorca dostępu do pamięci, aby zwiększyć wydajność środowiska uruchomieniowego. Jednak z punktu widzenia języka C++ funkcja nie ma zauważalnego efektu i może nic nie robić.|
|__rdpmccntr64||niepodpisane __int64 \__rdpmccntr64 (void)|
|__sev|Sev|void __sev(void)|
|__static_assert||void __static_assert(int, const \*char)|
|__swi|Svc|unsigned int __swi(unsigned int, ...)|
|__trap|BKPT (bkpt)|int __trap(int, ...)|
|__wfe|Fronton internetowy|void __wfe(void)|
|__wfi|Wfi|void __wfi(void)|
|_AddSatInt|Funkcja QADD|int _AddSatInt(int, int)|
|_CopyDoubleFromInt64||podwójne _CopyDoubleFromInt64(\__int64)|
|_CopyFloatFromInt32||_CopyFloatFromInt32 pływakowa(\__int32)|
|_CopyInt32FromFloat||__int32 _CopyInt32FromFloat(pływak)|
|_CopyInt64FromDouble||__int64 _CopyInt64FromDouble(podwójne)|
|_CountLeadingOnes||unsigned int _CountLeadingOnes(niepodpisane długo)|
|_CountLeadingOnes64||niepodpisane _CountLeadingOnes64 int (niepodpisane \__int64)|
|_CountLeadingSigns||unsigned int _CountLeadingSigns(long)|
|_CountLeadingSigns64||unsigned int _CountLeadingSigns64(\__int64)|
|_CountLeadingZeros||unsigned int _CountLeadingZeros(niepodpisane długo)|
|_CountLeadingZeros64||niepodpisane int _CountLeadingZeros64 (niepodpisane \__int64)|
|_CountOneBits||unsigned int _CountOneBits(niepodpisane długo)|
|_CountOneBits64||niepodpisane _CountOneBits64 int (niepodpisane \__int64)|
|_DAddSatInt|QDADD ( QDADD )|int _DAddSatInt(int, int)|
|_DSubSatInt|Z O.O.|int _DSubSatInt(int, int)|
|_isunordered||int _isunordered (podwójne, podwójne)|
|_isunorderedf||int _isunorderedf(pływak, pływak)|
|_MoveFromCoprocessor|Mrc|unsigned int _MoveFromCoprocessor(unsigned int, unsigned int, unsigned int, unsigned int, unsigned int)<br /><br /> Odczytuje dane z koproctworzycza ARM przy użyciu instrukcji transferu danych koprocsora. Aby uzyskać więcej informacji, zobacz [_MoveFromCoprocessor, _MoveFromCoprocessor2](#MoveFromCo).|
|_MoveFromCoprocessor2|MRC2 (właśc.|unsigned int _MoveFromCoprocessor2(unsigned int, unsigned int, unsigned int, unsigned int, unsigned int)<br /><br /> Odczytuje dane z koproctworzycza ARM przy użyciu instrukcji transferu danych koprocsora. Aby uzyskać więcej informacji, zobacz [_MoveFromCoprocessor, _MoveFromCoprocessor2](#MoveFromCo).|
|_MoveFromCoprocessor64|MRRC|niepodpisane __int64 _MoveFromCoprocessor64(niepodpisane int, niepodpisane int, niepodpisane int)<br /><br /> Odczytuje dane z koproctworzycza ARM przy użyciu instrukcji transferu danych koprocsora. Aby uzyskać więcej informacji, zobacz [_MoveFromCoprocessor64](#MoveFromCo64).|
|_MoveToCoprocessor|Mcr|void _MoveToCoprocessor(unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int)<br /><br /> Odczytuje dane z koproctworzycza ARM przy użyciu instrukcji transferu danych koprocsora. Aby uzyskać więcej informacji, zobacz [_MoveToCoprocessor, _MoveToCoprocessor2](#MoveToCo).|
|_MoveToCoprocessor2|McR2 (własnach)|void _MoveToCoprocessor2(unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int)<br /><br /> Odczytuje dane z koproctworzycza ARM przy użyciu instrukcji transferu danych koprocsora. Aby uzyskać więcej informacji, zobacz [_MoveToCoprocessor, _MoveToCoprocessor2](#MoveToCo).|
|_MoveToCoprocessor64|Okręg wyborczy MCRR|void _MoveToCoprocessor64(niepodpisane \__int64, niepodpisane int, niepodpisane int, niepodpisane int)<br /><br /> Odczytuje dane z koproctworzycza ARM przy użyciu instrukcji transferu danych koprocsora. Aby uzyskać więcej informacji, zobacz [_MoveToCoprocessor64](#MoveToCo64).|
|_MulHigh||długi _MulHigh (długi, długi)|
|_MulUnsignedHigh||niepodpisane długie _MulUnsignedHigh (niepodpisane długie, niepodpisane długie)|
|_ReadBankedReg|Pani|int _ReadBankedReg(int _Reg)|
|_ReadStatusReg|Pani|int _ReadStatusReg(int)|
|_SubSatInt|funkcja QSUB|int _SubSatInt(int, int)|
|_WriteBankedReg|MSR|void _WriteBankedReg (int _Value, int _Reg)|
|_WriteStatusReg|MSR|void _WriteStatusReg(int, int, int)|

[[Powrót do góry](#top)]

### <a name="memory-barrier-restrictions"></a><a name="BarrierRestrictions"></a>Ograniczenia bariery pamięci

Funkcje `__dmb` wewnętrzne (bariera pamięci `__dsb` danych), (bariera `__isb` synchronizacji danych) i (bariera synchronizacji instrukcji) używają następujących wstępnie zdefiniowanych wartości, aby określić ograniczenie bariery pamięci pod względem domeny udostępniania i rodzaju dostępu, na który ma wpływ operacja.

|Wartość ograniczenia|Opis|
|-----------------------|-----------------|
|_ARM_BARRIER_SY|Pełny system, odczyty i zapisy.|
|_ARM_BARRIER_ST|Pełny system, zapisuje tylko.|
|_ARM_BARRIER_ISH|Wewnętrzna sharable, odczytuje i pisze.|
|_ARM_BARRIER_ISHST|Wewnętrzna sharable, pisze tylko.|
|_ARM_BARRIER_NSH|Niezbywalne, odczytuje i pisze.|
|_ARM_BARRIER_NSHST|Nie sharable, zapisuje tylko.|
|_ARM_BARRIER_OSH|Zewnętrzna sharable, odczytuje i zapisuje.|
|_ARM_BARRIER_OSHST|Zewnętrzna sharable, zapisuje tylko.|

W `__isb` przypadku wewnętrznych jedynym ograniczeniem, które jest obecnie ważne, jest _ARM_BARRIER_SY; wszystkie inne wartości są zarezerwowane przez architekturę.

### <a name="__iso_volatile_loadstore-intrinsics"></a><a name="IsoVolatileLoadStore"></a>__iso_volatile_load/magazyn

Te funkcje wewnętrzne jawnie wykonywać obciążenia i magazyny, które nie podlegają optymalizacji kompilatora.

```C
__int16 __iso_volatile_load16(const volatile __int16 * Location);
__int32 __iso_volatile_load32(const volatile __int32 * Location);
__int64 __iso_volatile_load64(const volatile __int64 * Location);
__int8 __iso_volatile_load8(const volatile __int8 * Location);

void __iso_volatile_store16(volatile __int16 * Location, __int16 Value);
void __iso_volatile_store32(volatile __int32 * Location, __int32 Value);
void __iso_volatile_store64(volatile __int64 * Location, __int64 Value);
void __iso_volatile_store8(volatile __int8 * Location, __int8 Value);
```

#### <a name="parameters"></a>Parametry

*Lokalizacji*\
Adres lokalizacji pamięci do odczytu lub zapisu.

*Wartość*\
Wartość do zapisu do określonej lokalizacji pamięci (magazyn tylko wewnętrzne).

#### <a name="return-value-load-intrinsics-only"></a>Wartość zwracana (tylko wykastowe obciążenie)

Wartość lokalizacji pamięci określonej przez `Location`program .

#### <a name="remarks"></a>Uwagi

Można użyć `__iso_volatile_load8/16/32/64` i `__iso_volatile_store8/16/32/64` intrinsics jawnie wykonywać dostępy do pamięci, które nie podlegają optymalizacji kompilatora. Kompilator nie można usunąć, syntetyzować lub zmienić względną kolejność tych operacji, ale nie generuje niejawne bariery pamięci sprzętowej. W związku z tym sprzęt może nadal ponownie zasądzać zauważalne dostępy do pamięci w wielu wątkach. Dokładniej, te elementy wewnętrzne są równoważne następującym wyrażeniom skompilowanym w **/volatile:iso**.

```cpp
int a = __iso_volatile_load32(p);    // equivalent to: int a = *(const volatile __int32*)p;
__iso_volatile_store32(p, a);        // equivalent to: *(volatile __int32*)p = a;
```

Należy zauważyć, że wewnętrzne wskaźniki wziąć volatile wskaźniki w celu uwzględnienia zmiennych lotnych. Jednak nie ma żadnych wymagań lub zalecenia, aby użyć wskaźników nietrwałych jako argumenty. Semantyka tych operacji są dokładnie takie same, jeśli używany jest typ zwykły, nieulotny.

Aby uzyskać więcej informacji na temat argumentu wiersza polecenia **/volatile:iso,** zobacz [/volatile (volatile Keyword Interpretation)](../build/reference/volatile-volatile-keyword-interpretation.md).

### <a name="_movefromcoprocessor-_movefromcoprocessor2"></a><a name="MoveFromCo"></a>_MoveFromCoprocessor, _MoveFromCoprocessor2

Te wewnętrzne funkcje odczytywać dane z koprocarzy ARM przy użyciu instrukcji transferu danych koprociarka.

```C
int _MoveFromCoprocessor(
      unsigned int coproc,
      unsigned int opcode1,
      unsigned int crn,
      unsigned int crm,
      unsigned int opcode2
);

int _MoveFromCoprocessor2(
      unsigned int coproc,
      unsigned int opcode1,
      unsigned int crn,
      unsigned int crm,
      unsigned int opcode2
);
```

#### <a name="parameters"></a>Parametry

*coproc (coproc)*\
Liczba koprociarka w zakresie od 0 do 15.

*opcode1*\
Kod operacyjny specyficzny dla koprocsora w zakresie od 0 do 7

*Crn*\
Numer rejestru koprocsorów, w zakresie od 0 do 15, który określa pierwszy argument do instrukcji.

*Crm*\
Numer rejestru koprocsorów w zakresie od 0 do 15, który określa dodatkowy operand źródłowy lub docelowy.

*opcode2*\
Dodatkowy kod opcode specyficzny dla koprocasora w zakresie od 0 do 7.

#### <a name="return-value"></a>Wartość zwracana

Wartość, która jest odczytywana z koprocasora.

#### <a name="remarks"></a>Uwagi

Wartości wszystkich pięciu parametrów wewnętrznych musi być wyrażenia stałe, które są znane w czasie kompilacji.

`_MoveFromCoprocessor`korzysta z instrukcji MRC; `_MoveFromCoprocessor2` wykorzystuje MRC2. Parametry odpowiadają pola bitowe, które są kodowane bezpośrednio do słowa instrukcji. Interpretacja parametrów jest zależna od koprocasora. Aby uzyskać więcej informacji, zobacz instrukcję dla danego koprocasora.

### <a name="_movefromcoprocessor64"></a><a name="MoveFromCo64"></a>_MoveFromCoprocessor64

Odczytuje dane z koprocektorów ARM przy użyciu instrukcji transferu danych koprocsora.

```C
unsigned __int64 _MoveFromCoprocessor64(
      unsigned int coproc,
      unsigned int opcode1,
      unsigned int crm,
);
```

#### <a name="parameters"></a>Parametry

*coproc (coproc)*\
Liczba koprociarka w zakresie od 0 do 15.

*opcode1*\
Kod opcode specyficzny dla koprocsora w zakresie od 0 do 15.

*Crm*\
Numer rejestru koprocsorów w zakresie od 0 do 15, który określa dodatkowy operand źródłowy lub docelowy.

**Zwraca wartość**

Wartość, która jest odczytywana z koprocasora.

#### <a name="remarks"></a>Uwagi

Wartości wszystkich trzech parametrów wewnętrznych musi być wyrażenia stałe, które są znane w czasie kompilacji.

`_MoveFromCoprocessor64`korzysta z instrukcji MRRC. Parametry odpowiadają pola bitowe, które są kodowane bezpośrednio do słowa instrukcji. Interpretacja parametrów jest zależna od koprocasora. Aby uzyskać więcej informacji, zobacz instrukcję dla danego koprocasora.

### <a name="_movetocoprocessor-_movetocoprocessor2"></a><a name="MoveToCo"></a>_MoveToCoprocessor, _MoveToCoprocessor2

Te wewnętrzne funkcje zapisują dane do koprocewników ARM przy użyciu instrukcji transferu danych koprocasora.

```C
void _MoveToCoprocessor(
      unsigned int value,
      unsigned int coproc,
      unsigned int opcode1,
      unsigned int crn,
      unsigned int crm,
      unsigned int opcode2
);

void _MoveToCoprocessor2(
      unsigned int value,
      unsigned int coproc,
      unsigned int opcode1,
      unsigned int crn,
      unsigned int crm,
      unsigned int opcode2
);
```

#### <a name="parameters"></a>Parametry

*Wartość*\
Wartość, która ma zostać zapisana w koprocasorze.

*coproc (coproc)*\
Liczba koprociarka w zakresie od 0 do 15.

*opcode1*\
Kod opcode specyficzny dla koprocsora w zakresie od 0 do 7.

*Crn*\
Numer rejestru koprocsorów, w zakresie od 0 do 15, który określa pierwszy argument do instrukcji.

*Crm*\
Numer rejestru koprocsorów w zakresie od 0 do 15, który określa dodatkowy operand źródłowy lub docelowy.

*opcode2*\
Dodatkowy kod opcode specyficzny dla koprocasora w zakresie od 0 do 7.

#### <a name="return-value"></a>Wartość zwracana

Brak.

#### <a name="remarks"></a>Uwagi

Wartości `coproc`, `opcode1`, `crn`, `crm`i `opcode2` parametry wewnętrzne muszą być wyrażenia stałe, które są znane w czasie kompilacji.

`_MoveToCoprocessor`korzysta z instrukcji MCR; `_MoveToCoprocessor2` wykorzystuje MCR2. Parametry odpowiadają pola bitowe, które są kodowane bezpośrednio do słowa instrukcji. Interpretacja parametrów jest zależna od koprocasora. Aby uzyskać więcej informacji, zobacz instrukcję dla danego koprocasora.

### <a name="_movetocoprocessor64"></a><a name="MoveToCo64"></a>_MoveToCoprocessor64

Te wewnętrzne funkcje zapisują dane do koprocewników ARM przy użyciu instrukcji transferu danych koprocasora.

```
void _MoveFromCoprocessor64(
      unsigned __int64 value,
      unsigned int coproc,
      unsigned int opcode1,
      unsigned int crm,
);
```

#### <a name="parameters"></a>Parametry

*coproc (coproc)*\
Liczba koprociarka w zakresie od 0 do 15.

*opcode1*\
Kod opcode specyficzny dla koprocsora w zakresie od 0 do 15.

*Crm*\
Numer rejestru koprocsorów w zakresie od 0 do 15, który określa dodatkowy operand źródłowy lub docelowy.

#### <a name="return-value"></a>Wartość zwracana

Brak.

#### <a name="remarks"></a>Uwagi

Wartości `coproc`, `opcode1`i `crm` parametry wewnętrzne muszą być wyrażenia stałe, które są znane w czasie kompilacji.

`_MoveFromCoprocessor64`korzysta z instrukcji MCRR. Parametry odpowiadają pola bitowe, które są kodowane bezpośrednio do słowa instrukcji. Interpretacja parametrów jest zależna od koprocasora. Aby uzyskać więcej informacji, zobacz instrukcję dla danego koprocasora.

## <a name="arm-support-for-intrinsics-from-other-architectures"></a><a name="I"></a>Obsługa ARM dla wewnętrznego z innych architektur

W poniższej tabeli wymieniono elementy wewnętrzne innych architektur, które są obsługiwane na platformach ARM. Gdy zachowanie wewnętrznej na ARM różni się od jego zachowania na innych architekturach sprzętu, dodatkowe szczegóły są zauważyć.

|Nazwa funkcji|Prototyp funkcji|
|-------------------|------------------------|
|__assume|nieważne __assume(int)|
|__code_seg|void __code_seg(const char) \*|
|__debugbreak|void __cdecl \__debugbreak(void)|
|__fastfail|__declspec(noreturn) void \__fastfail(unsigned int)|
|__nop|void __nop(void) **Uwaga:** Na platformach ARM ta funkcja generuje instrukcję NOP, jeśli jest zaimplementowana w architekturze docelowej; w przeciwnym razie generowana jest alternatywna instrukcja, która nie `MOV r8, r8`zmienia stanu programu lub procesora — na przykład . Jest funkcjonalnie odpowiednik \__nop nieodłącznym dla innych architektur sprzętowych. Ponieważ instrukcja, która nie ma wpływu na stan programu lub procesora CPU może być ignorowana przez architekturę docelową jako optymalizacja, instrukcja nie musi zużywać cykli procesora CPU. W związku z tym \_nie należy używać _nop wewnętrzne do manipulowania czasem wykonywania sekwencji kodu, chyba że masz pewność, jak będzie zachowywać się procesor CPU. Zamiast tego można użyć \__nop wewnętrznej, aby wyrównać następną instrukcję do określonego 32-bitowego adresu granicznego.|
|__yield|void __yield(void) **Uwaga:** Na platformach ARM ta funkcja generuje instrukcję YIELD, która wskazuje, że wątek wykonuje zadanie, które może być tymczasowo zawieszone w wykonywaniu — na przykład spinlock — bez negatywnego wpływu na program. Umożliwia procesorowi CPU wykonywanie innych zadań podczas cykli wykonywania, które w przeciwnym razie zostałyby zmarnowane.|
|_AddressOfReturnAddress|void \* _AddressOfReturnAddress(void)|
|_BitScanForward|niepodpisane _BitScanForward char (niepodpisane długie \* _Index, niepodpisane długie _Mask)|
|_BitScanReverse|niepodpisane _BitScanReverse char (niepodpisane długie \* _Index, niepodpisane długie _Mask)|
|_bittest|niepodpisany znak _bittest (długi \*const, długi)|
|_bittestandcomplement|niepodpisany znak _bittestandcomplement (długi, \*długi)|
|_bittestandreset|niepodpisany znak _bittestandreset \*(długi, długi)|
|_bittestandset|niepodpisany znak _bittestandset (długi, \*długi)|
|_byteswap_uint64|niepodpisane __int64 \__byteswap_uint64 _cdecl (_int64 niepodpisane) \_|
|_byteswap_ulong|niepodpisane długie __cdecl _byteswap_ulong (niepodpisane długie)|
|_byteswap_ushort|niepodpisane krótkie _byteswap_ushort __cdecl (niepodpisane krótkie)|
|_disable|void __cdecl _disable(void) **Uwaga:** Na platformach ARM ta funkcja generuje instrukcję CPSID; jest dostępny tylko jako nieodłączny element.|
|_enable|void __cdecl _enable(void) **Uwaga:** Na platformach ARM ta funkcja generuje instrukcję CPSIE; jest dostępny tylko jako nieodłączny element.|
|_lrotl|niepodpisane długie __cdecl _lrotl (niepodpisane długie, int)|
|_lrotr|niepodpisane długie __cdecl _lrotr (niepodpisane długie, int)|
|_ReadBarrier|void _ReadBarrier(void)|
|_ReadWriteBarrier|void _ReadWriteBarrier(void)|
|_ReturnAddress|void \* _ReturnAddress(void)|
|_rotl|unsigned int __cdecl _rotl (unsigned int _Value, int _Shift)|
|_rotl16|niepodpisane krótkie _rotl16 (niepodpisane krótkie _Value, niepodpisane _Shift char)|
|_rotl64|niepodpisane __int64 \__cdecl _rotl64 (_Value _int64 niepodpisane, \_int _Shift)|
|_rotl8|niepodpisane _rotl8 char(niepodpisane _Value char, niepodpisane char _Shift)|
|_rotr|unsigned int __cdecl _rotr (unsigned int _Value, int _Shift)|
|_rotr16|niepodpisane krótkie _rotr16 (niepodpisane krótkie _Value, niepodpisane _Shift char)|
|_rotr64|niepodpisane __int64 \__cdecl _rotr64 (_Value _int64 niepodpisane, \_int _Shift)|
|_rotr8|niepodpisane _rotr8 char(niepodpisane _Value char, niepodpisane char _Shift)|
|_setjmpex|int __cdecl _setjmpex(jmp_buf)|
|_WriteBarrier|void _WriteBarrier(void)|

[[Powrót do góry](#top)]

## <a name="interlocked-intrinsics"></a>Zablokowane środki wewnętrzne

Interlocked intrinsics to zestaw wewnętrznych, które są używane do wykonywania operacji atomowego odczytu i modyfikowania zapisu. Niektóre z nich są wspólne dla wszystkich platform. Są one wymienione oddzielnie tutaj, ponieważ istnieje duża liczba z nich, ale ponieważ ich definicje są w większości zbędne, łatwiej jest myśleć o nich w kategoriach ogólnych. Ich nazwy mogą służyć do wyprowadzania dokładnych zachowań.

W poniższej tabeli podsumowano obsługę ARM nie-bittest zablokowane wewnętrzne. Każda komórka w tabeli odpowiada nazwie, która jest pochodną przez dołączenie nazwy operacji w lewej komórce wiersza i nazwy `_Interlocked`typu w komórce najwyższej wielkości kolumny do . Na przykład komórka na przecięciu `Xor` `8` wiersza i `_InterlockedXor8` kolumny odpowiada i jest w pełni obsługiwana. Większość obsługiwanych funkcji oferuje te opcjonalne `_acq`przyrostki: , `_rel`, i `_nf`. Sufiks `_acq` wskazuje semantyczne "nabyć", `_rel` a sufiks oznacza semantyczną "release". Przyrostek `_nf` lub "bez ogrodzenia" jest unikatowy dla ARM i jest omówiony w następnej sekcji.

||8|16|32|64|P|
|-|-------|--------|--------|--------|-------|
|Dodaj|Brak|Brak|Pełne|Pełne|Brak|
|And|Pełne|Pełne|Pełne|Pełne|Brak|
|Compareexchange|Pełne|Pełne|Pełne|Pełne|Pełne|
|Zmniejszyć|Brak|Pełne|Pełne|Pełne|Brak|
|Exchange|Częściowo|Częściowo|Częściowo|Częściowo|Częściowo|
|Wymiana Addd|Pełne|Pełne|Pełne|Pełne|Brak|
|Przyrost|Brak|Pełne|Pełne|Pełne|Brak|
|Lub|Pełne|Pełne|Pełne|Pełne|Brak|
|Xor|Pełne|Pełne|Pełne|Pełne|Brak|

Klucz:

- **Pełna**: obsługuje `_acq` `_rel`zwykły, `_nf` , i formy.

- **Częściowe**: `_acq`obsługuje `_nf` zwykły, i formy.

- **Brak:** Nie obsługiwane

### <a name="_nf-no-fence-suffix"></a><a name="nf_suffix"></a>_nf (bez ogrodzenia) Przyrostek

Sufiks `_nf` "bez ogrodzenia" wskazuje, że operacja nie zachowuje się jak żadna bariera pamięci, `_acq`w `_rel`przeciwieństwie do pozostałych trzech form (zwykły, i ), które zachowują się jak pewnego rodzaju bariera. Jednym z możliwych `_nf` zastosowań formularzy jest obsługa licznika statystyk, który jest aktualizowany przez wiele wątków w tym samym czasie, ale którego wartość nie jest używana w inny sposób podczas wykonywania wielu wątków.

### <a name="list-of-interlocked-intrinsics"></a>Lista zablokowanych wewnętrznych

|Nazwa funkcji|Prototyp funkcji|
|-------------------|------------------------|
|_InterlockedAdd|długi _InterlockedAdd (długi \*_volatile, długi)|
|_InterlockedAdd64|__int64 _InterlockedAdd64(\__int64 lotny \*, \__int64)|
|_InterlockedAdd64_acq|__int64 _InterlockedAdd64_acq _int64 _int64\_lotnych \* \_|
|_InterlockedAdd64_nf|__int64 _InterlockedAdd64_nf(\__int64 lotny \*, \__int64)|
|_InterlockedAdd64_rel|__int64 _InterlockedAdd64_rel(\__int64 lotny, \* \__int64)|
|_InterlockedAdd_acq|długi _InterlockedAdd_acq (długi lotny, \*długi)|
|_InterlockedAdd_nf|długi _InterlockedAdd_nf (długi lotny, \*długi)|
|_InterlockedAdd_rel|długi _InterlockedAdd_rel (długi lotny, \*długi)|
|_InterlockedAnd|długi _InterlockedAnd (długi lotny, \*długi)|
|_InterlockedAnd16|krótki _InterlockedAnd16 (krótki lotny, \*krótki)|
|_InterlockedAnd16_acq|krótki _InterlockedAnd16_acq (krótki lotny, \*krótki)|
|_InterlockedAnd16_nf|krótki _InterlockedAnd16_nf (krótki \*lotny, krótki)|
|_InterlockedAnd16_rel|krótki _InterlockedAnd16_rel (krótki \*lotny, krótki)|
|_InterlockedAnd64|__int64 _InterlockedAnd64(\__int64 lotny \*, \__int64)|
|_InterlockedAnd64_acq|__int64 _InterlockedAnd64_acq _int64 _int64\__int64 \* \_|
|_InterlockedAnd64_nf|__int64 _InterlockedAnd64_nf(\__int64 lotny \*, \__int64)|
|_InterlockedAnd64_rel|__int64 _InterlockedAnd64_rel(\__int64 lotny \*, \__int64)|
|_InterlockedAnd8|char _InterlockedAnd8(char volatile \*, char)|
|_InterlockedAnd8_acq|char _InterlockedAnd8_acq(char volatile \*, char)|
|_InterlockedAnd8_nf|char _InterlockedAnd8_nf(char volatile \*, char)|
|_InterlockedAnd8_rel|char _InterlockedAnd8_rel(char volatile \*, char)|
|_InterlockedAnd_acq|długi _InterlockedAnd_acq (długi lotny, \*długi)|
|_InterlockedAnd_nf|długi _InterlockedAnd_nf (długi lotny, \*długi)|
|_InterlockedAnd_rel|długi _InterlockedAnd_rel (długi lotny, \*długi)|
|_InterlockedCompareExchange|długi __cdecl _InterlockedCompareExchange (długi lotny, \*długi, długi)|
|_InterlockedCompareExchange16|krótki _InterlockedCompareExchange16 (krótki lotny, \*krótki, krótki)|
|_InterlockedCompareExchange16_acq|krótki _InterlockedCompareExchange16_acq (krótki \*lotny, krótki, krótki)|
|_InterlockedCompareExchange16_nf|krótki _InterlockedCompareExchange16_nf (krótki lotny, \*krótki, krótki)|
|_InterlockedCompareExchange16_rel|krótki _InterlockedCompareExchange16_rel (krótki lotny, \*krótki, krótki)|
|_InterlockedCompareExchange64|\___int64 _InterlockedCompareExchange64( _int64 \*lotny, \__int64, \__int64)|
|_InterlockedCompareExchange64_acq|\___int64 _InterlockedCompareExchange64_acq( _int64 \*lotny, \__int64, \__int64)|
|_InterlockedCompareExchange64_nf|\___int64 _InterlockedCompareExchange64_nf( _int64 \*lotny, \__int64, \__int64)|
|_InterlockedCompareExchange64_rel|\___int64 _InterlockedCompareExchange64_rel( _int64 \*lotny, \__int64, \__int64)|
|_InterlockedCompareExchange8|char _InterlockedCompareExchange8(char volatile \*, char, char)|
|_InterlockedCompareExchange8_acq|char _InterlockedCompareExchange8_acq(char volatile, \*char, char)|
|_InterlockedCompareExchange8_nf|char _InterlockedCompareExchange8_nf(char volatile \*, char, char)|
|_InterlockedCompareExchange8_rel|char _InterlockedCompareExchange8_rel(char volatile \*, char, char)|
|_InterlockedCompareExchangePointer|void \* \* _InterlockedCompareExchangePointer(void volatile \*, \*void \*, void )|
|_InterlockedCompareExchangePointer_acq|void \* \* _InterlockedCompareExchangePointer_acq(void volatile \*, \*void \*, void )|
|_InterlockedCompareExchangePointer_nf|void \* \* _InterlockedCompareExchangePointer_nf(void volatile \*, \*void \*, void )|
|_InterlockedCompareExchangePointer_rel|void \* \* _InterlockedCompareExchangePointer_rel(void volatile \*, \*void \*, void )|
|_InterlockedCompareExchange_acq|długi _InterlockedCompareExchange_acq (długi lotny, \*długi, długi)|
|_InterlockedCompareExchange_nf|długi _InterlockedCompareExchange_nf (długi lotny, \*długi, długi)|
|_InterlockedCompareExchange_rel|długi _InterlockedCompareExchange_rel (długi lotny, \*długi, długi)|
|_InterlockedDecrement|długi __cdecl _InterlockedDecrement (długi lotny) \*|
|_InterlockedDecrement16|krótki _InterlockedDecrement16 (krótki lotny) \*|
|_InterlockedDecrement16_acq|krótki _InterlockedDecrement16_acq (krótki lotny) \*|
|_InterlockedDecrement16_nf|krótki _InterlockedDecrement16_nf (krótki \*lotny)|
|_InterlockedDecrement16_rel|krótki _InterlockedDecrement16_rel (krótki lotny) \*|
|_InterlockedDecrement64|__int64 _InterlockedDecrement64(\__int64 lotny) \*|
|_InterlockedDecrement64_acq|__int64 _InterlockedDecrement64_acq(\__int64 lotny) \*|
|_InterlockedDecrement64_nf|__int64 _InterlockedDecrement64_nf(\__int64 lotny) \*|
|_InterlockedDecrement64_rel|__int64 _InterlockedDecrement64_rel(\__int64 lotny) \*|
|_InterlockedDecrement_acq|długi _InterlockedDecrement_acq (długi lotny) \*|
|_InterlockedDecrement_nf|długi _InterlockedDecrement_nf(długi lotny) \*|
|_InterlockedDecrement_rel|długi _InterlockedDecrement_rel(długi lotny) \*|
|_InterlockedExchange|długi __cdecl _InterlockedExchange (długi lotny \* _Target, długi)|
|_InterlockedExchange16|krótki _InterlockedExchange16 (krótki lotny \* _Target, krótki)|
|_InterlockedExchange16_acq|krótki _InterlockedExchange16_acq (krótki lotny \* _Target, krótki)|
|_InterlockedExchange16_nf|krótki _InterlockedExchange16_nf (krótki lotny \* _Target, krótki)|
|_InterlockedExchange64|__int64 _InterlockedExchange64(\__int64 lotnych \* _Target, \__int64)|
|_InterlockedExchange64_acq|__int64 _InterlockedExchange64_acq(\__int64 lotny \* _Target, \__int64)|
|_InterlockedExchange64_nf|__int64 _InterlockedExchange64_nf(\__int64 lotnych \* _Target, \__int64)|
|_InterlockedExchange8|char _InterlockedExchange8(char volatile \* _Target, char)|
|_InterlockedExchange8_acq|char _InterlockedExchange8_acq(char volatile \* _Target, char)|
|_InterlockedExchange8_nf|char _InterlockedExchange8_nf(char volatile \* _Target, char)|
|_InterlockedExchangeAdd|długi __cdecl _InterlockedExchangeAdd (długi lotny, \*długi)|
|_InterlockedExchangeAdd16|krótki _InterlockedExchangeAdd16 (krótki lotny, \*krótki)|
|_InterlockedExchangeAdd16_acq|krótki _InterlockedExchangeAdd16_acq (krótki lotny, \*krótki)|
|_InterlockedExchangeAdd16_nf|krótki _InterlockedExchangeAdd16_nf (krótki \*lotny, krótki)|
|_InterlockedExchangeAdd16_rel|krótki _InterlockedExchangeAdd16_rel (krótki \*lotny, krótki)|
|_InterlockedExchangeAdd64|__int64 _InterlockedExchangeAdd64(\__int64 lotny \*, \__int64)|
|_InterlockedExchangeAdd64_acq|__int64 _InterlockedExchangeAdd64_acq(\__int64 lotny \*, \__int64)|
|_InterlockedExchangeAdd64_nf|__int64 _InterlockedExchangeAdd64_nf(\__int64 lotny \*, \__int64)|
|_InterlockedExchangeAdd64_rel|__int64 _InterlockedExchangeAdd64_rel(\__int64 lotny \*, \__int64)|
|_InterlockedExchangeAdd8|char _InterlockedExchangeAdd8(char volatile \*, char)|
|_InterlockedExchangeAdd8_acq|char _InterlockedExchangeAdd8_acq(char volatile \*, char)|
|_InterlockedExchangeAdd8_nf|char _InterlockedExchangeAdd8_nf(char volatile \*, char)|
|_InterlockedExchangeAdd8_rel|char _InterlockedExchangeAdd8_rel(char volatile \*, char)|
|_InterlockedExchangeAdd_acq|długi _InterlockedExchangeAdd_acq (długi lotny, \*długi)|
|_InterlockedExchangeAdd_nf|długi _InterlockedExchangeAdd_nf (długi lotny, \*długi)|
|_InterlockedExchangeAdd_rel|długi _InterlockedExchangeAdd_rel (długi lotny, \*długi)|
|_InterlockedExchangePointer|void \* _InterlockedExchangePointer(void \* volatile \* _Target, void) \*|
|_InterlockedExchangePointer_acq|void \* _InterlockedExchangePointer_acq(void \* volatile \* _Target, void) \*|
|_InterlockedExchangePointer_nf|void \* _InterlockedExchangePointer_nf(void \* volatile \* _Target, void) \*|
|_InterlockedExchange_acq|długi _InterlockedExchange_acq (długi \* lotny _Target, długi)|
|_InterlockedExchange_nf|długi _InterlockedExchange_nf (długi \* lotny _Target, długi)|
|_InterlockedIncrement|długi __cdecl _InterlockedIncrement (długo lotny) \*|
|_InterlockedIncrement16|krótki _InterlockedIncrement16 (krótki lotny) \*|
|_InterlockedIncrement16_acq|krótki _InterlockedIncrement16_acq (krótki lotny) \*|
|_InterlockedIncrement16_nf|krótki _InterlockedIncrement16_nf (krótki \*lotny)|
|_InterlockedIncrement16_rel|krótki _InterlockedIncrement16_rel (krótki lotny) \*|
|_InterlockedIncrement64|__int64 _InterlockedIncrement64(\__int64 lotny) \*|
|_InterlockedIncrement64_acq|__int64 _InterlockedIncrement64_acq(\__int64 lotny) \*|
|_InterlockedIncrement64_nf|__int64 _InterlockedIncrement64_nf(\__int64 lotny) \*|
|_InterlockedIncrement64_rel|__int64 _InterlockedIncrement64_rel(\__int64 lotny) \*|
|_InterlockedIncrement_acq|długi _InterlockedIncrement_acq (długi lotny) \*|
|_InterlockedIncrement_nf|długi _InterlockedIncrement_nf(długi lotny) \*|
|_InterlockedIncrement_rel|długi _InterlockedIncrement_rel (długi lotny) \*|
|_InterlockedOr|długi _InterlockedOr (długi lotny, \*długi)|
|_InterlockedOr16|krótki _InterlockedOr16 (krótki \*lotny, krótki)|
|_InterlockedOr16_acq|krótki _InterlockedOr16_acq (krótki lotny, \*krótki)|
|_InterlockedOr16_nf|krótki _InterlockedOr16_nf (krótki lotny, \*krótki)|
|_InterlockedOr16_rel|krótki _InterlockedOr16_rel (krótki lotny, \*krótki)|
|_InterlockedOr64|__int64 _InterlockedOr64(\__int64 lotny, \* \__int64)|
|_InterlockedOr64_acq|__int64 _InterlockedOr64_acq(\__int64 lotny \*, \__int64)|
|_InterlockedOr64_nf|__int64 _InterlockedOr64_nf _int64(\__int64 lotny) \* \_|
|_InterlockedOr64_rel|__int64 _InterlockedOr64_rel(\__int64 lotny \*, \__int64)|
|_InterlockedOr8|char _InterlockedOr8(char volatile \*, char)|
|_InterlockedOr8_acq|char _InterlockedOr8_acq(char volatile \*, char)|
|_InterlockedOr8_nf|char _InterlockedOr8_nf(char volatile \*, char)|
|_InterlockedOr8_rel|char _InterlockedOr8_rel(char volatile \*, char)|
|_InterlockedOr_acq|długi _InterlockedOr_acq (długi lotny, \*długi)|
|_InterlockedOr_nf|długi _InterlockedOr_nf (długi lotny, \*długi)|
|_InterlockedOr_rel|długi _InterlockedOr_rel (długi lotny, \*długi)|
|_InterlockedXor|długi _InterlockedXor (długi \*lotny, długi)|
|_InterlockedXor16|krótki _InterlockedXor16 (krótki lotny, \*krótki)|
|_InterlockedXor16_acq|krótki _InterlockedXor16_acq (krótki \*lotny, krótki)|
|_InterlockedXor16_nf|krótki _InterlockedXor16_nf (krótki lotny, \*krótki)|
|_InterlockedXor16_rel|krótki _InterlockedXor16_rel (krótki \*lotny, krótki)|
|_InterlockedXor64|__int64 _InterlockedXor64(\__int64 lotny, \* \__int64)|
|_InterlockedXor64_acq|__int64 _InterlockedXor64_acq _int64 _int64 lotnych(\__int64 \*lotnych) \_|
|_InterlockedXor64_nf|__int64 _InterlockedXor64_nf(\__int64 lotny \*, \__int64)|
|_InterlockedXor64_rel|__int64 _InterlockedXor64_rel(\__int64 lotny \*, \__int64)|
|_InterlockedXor8|char _InterlockedXor8(char volatile \*, char)|
|_InterlockedXor8_acq|char _InterlockedXor8_acq(char volatile \*, char)|
|_InterlockedXor8_nf|char _InterlockedXor8_nf(char volatile \*, char)|
|_InterlockedXor8_rel|char _InterlockedXor8_rel(char volatile \*, char)|
|_InterlockedXor_acq|długi _InterlockedXor_acq (długi lotny, \*długi)|
|_InterlockedXor_nf|długi _InterlockedXor_nf (długi \*lotny, długi)|
|_InterlockedXor_rel|długi _InterlockedXor_rel (długi lotny, \*długi)|

[[Powrót do góry](#top)]

### <a name="_interlockedbittest-intrinsics"></a>_interlockedbittest wewnętrzną

Wywiązuje się ze zwykłych powiązanych obrażeń testowych bitów są wspólne dla wszystkich platform. ARM `_acq`dodaje `_rel`, `_nf` i warianty, które po prostu zmodyfikować semantykę bariery operacji, jak opisano w [_nf (bez ogrodzenia) Sufiks](#nf_suffix) wcześniej w tym artykule.

|Nazwa funkcji|Prototyp funkcji|
|-------------------|------------------------|
|_interlockedbittestandreset|niepodpisany znak _interlockedbittestandreset (długi \*lotny, długi)|
|_interlockedbittestandreset_acq|niepodpisany znak _interlockedbittestandreset_acq (długi \*lotny, długi)|
|_interlockedbittestandreset_nf|niepodpisany znak _interlockedbittestandreset_nf (długi \*lotny, długi)|
|_interlockedbittestandreset_rel|niepodpisany znak _interlockedbittestandreset_rel (długi \*lotny, długi)|
|_interlockedbittestandset|niepodpisany znak _interlockedbittestandset (długi \*lotny, długi)|
|_interlockedbittestandset_acq|niepodpisany znak _interlockedbittestandset_acq (długi \*lotny, długi)|
|_interlockedbittestandset_nf|niepodpisany znak _interlockedbittestandset_nf (długi \*lotny, długi)|
|_interlockedbittestandset_rel|niepodpisany znak _interlockedbittestandset_rel (długi \*lotny, długi)|

[[Powrót do góry](#top)]

## <a name="see-also"></a>Zobacz też

[Wewnętrzne właściwości kompilatora](../intrinsics/compiler-intrinsics.md)\
[Arm64 wewnętrzną](arm64-intrinsics.md)\
[Odniesienie do asemblera ARM](../assembler/arm/arm-assembler-reference.md)\
[Odwołanie do języka C++](../cpp/cpp-language-reference.md)
