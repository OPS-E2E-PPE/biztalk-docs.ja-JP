---
title: 区切り記号の既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- known issues, delimiters
- delimiters
ms.assetid: 4eaacb3c-9d8d-43da-91dd-8bb25dec70e1
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6de686d136d0158315dfd00eba9690b8ffcbdccc
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36985651"
---
# <a name="delimiters-known-issues"></a>区切り記号の既知の問題
このセクションには、区切り記号のエラーを回避するために役立つ有用な情報が含まれています。  
  
## <a name="characters-not-recommended-to-be-used-as-delimiters"></a>文字が区切り記号として使用することをお勧めしません  
 使用することはない、次の文字区切り記号としてエラーが発生する可能性がありますをお勧めします。  
  
-   Null 文字  
  
-   スペース  
  
## <a name="extra-delimiters-in-a-header-or-body-field-cause-multiple-errors"></a>複数のエラーが発生する、ヘッダーまたは本文フィールド内の余分な区切り記号  
 HL7 V2 を内のフィールドに追加の区切り記号がある場合は。X のメッセージ、Microsoft BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) パーサーは 2 つのエラー メッセージを生成可能性があります XML 検証に関連する 1 つと、構造の検証に関連する他のです。  
  
## <a name="trailing-delimiters-permitted-in-hl7-batch-segments"></a>HL7 バッチ セグメントで許可されている末尾の区切り記号  
 HL7 のために末尾の区切り記号があることができ、末尾の区切り記号フラグでは、必ずしも FHS、BHS、BTS、および FTS など batch セグメントを定義した[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]セグメントをバッチ処理の末尾の区切り記号を検証しません。  
  
## <a name="see-also"></a>参照  
 [既知の問題](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)