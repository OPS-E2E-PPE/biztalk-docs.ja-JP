---
title: 区切り記号の既知の問題 |Microsoft ドキュメント
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
ms.openlocfilehash: 18168ade94eed99efff0a062904c14b387de6bcc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204690"
---
# <a name="delimiters-known-issues"></a>区切り記号の既知の問題
このセクションには、区切り記号のエラーを回避するために役立つ有用な情報が含まれています。  
  
## <a name="characters-not-recommended-to-be-used-as-delimiters"></a>文字が区切り記号として使用することをお勧めできません。  
 使用することはできません、次の文字区切り記号としてエラーが発生した可能性がありますをお勧めします。  
  
-   Null 文字  
  
-   スペース  
  
## <a name="extra-delimiters-in-a-header-or-body-field-cause-multiple-errors"></a>ヘッダーまたは本文フィールド内の余分な区切り記号が複数のエラーが発生します。  
 HL7 V2 内のフィールドに余分なデリミターがある場合は。メッセージ、x、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) パーサーは 2 つのエラー メッセージを生成可能性があります XML 検証に関連する 1 つと、他の検証に関連する構造。  
  
## <a name="trailing-delimiters-permitted-in-hl7-batch-segments"></a>HL7 バッチ セグメントで許可される末尾の区切り記号  
 HL7 定義されているバッチ セグメントなど、FHS、BHS、BTS、および FT 末尾の区切り記号には、末尾の区切り記号フラグ制約を受けないため[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]セグメントをバッチ処理の末尾の区切り記号では検証されません。  
  
## <a name="see-also"></a>参照  
 [既知の問題](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)