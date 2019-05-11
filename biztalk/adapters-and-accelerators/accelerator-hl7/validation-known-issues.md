---
title: 検証の既知の問題 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- known issues, validating
- validating, known issues
ms.assetid: 136596f2-ee0f-4ea9-918c-3608f2ee1be3
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 236cdfaca89068ad67b8f70138d926f4b60cedf1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65286444"
---
# <a name="validation-known-issues"></a>検証に関する既知の問題
このセクションには、検証エラーを回避するために役立つ有用な情報が含まれています。  
  
## <a name="disabling-xml-validation"></a>XML 検証を無効にします。  
 「本文検証セグメント」フラグ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]構成エクスプ ローラーは、XML 本文の検証を制御し、予期しない区切り文字と末尾の区切り記号の検証には含まれません。 メッセージが適切な区切り記号を持たない場合、メッセージを正常に解析できません。 メッセージを正常に解析できない場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]中間の有効な XML を生成することはできません。 「本文のセグメントを検証する」フラグを無効にするのでは、次に結果します。  
  
1.  空の必須フィールドです。  
  
2.  データ型は検証されません。  
  
3.  セグメントの構造の検証は行われません (セグメントの順序は検証されません)。  
  
## <a name="v2xml-acks-with-multiple-errors-will-fail-validation"></a>V2。複数のエラーで XML Ack 検証に失敗します  
 受信の V2 の場合。XML メッセージには、Microsoft BizTalk Accelerator for HL7 の 1 つ以上のエラーが含まれています ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) パーサーは、V2 生成可能性があります。Error フィールドに 1 つ以上のエラーで XML の確認 (ACK)。 このような V2。XML の確認には、HL7 標準では、パーサーが、V2 での 1 つだけのエラーを報告できるを指定するために、検証は失敗します。XML の ACK エラー フィールドです。  
  
## <a name="two-parsing-errors-are-logged-when-messages-in-the-batch-inbatch-out-scenario-contain-validation-errors"></a>2 つの解析エラーがログに記録時に、バッチ内のメッセージで/バッチ アウト シナリオは、検証エラーを含めることが  
 バッチ内の最初のメッセージで/バッチ アウト シナリオ (複数のメッセージがバッチ ヘッダーのないバッチ) には、検証エラーが含まれています。[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]イベント ログに 2 つのエラー ログに記録します。 最初のエラーが、バッチの最初のメッセージに関連し、2 番目のエラーに関連するメッセージの残りの部分。  
  
## <a name="restrictions-in-validating-field-length"></a>フィールドの長さの検証の制限  
 HL7 の複雑なデータ型は、のコンポーネントとサブコンポーネントで構成に関連付けられているフィールドです。 HL7 の規則は、長さと、フィールド レベルで、コンポーネントまたはサブコンポーネント レベルではなくオプションかどうかを指定します。 たとえば V2.4、HL7 は HD データ型と 180 文字の最大長である MSH3 を制御します。 HD は、HD1 セットは、現状、ST、として HD2 セット id。 hd3 はどれも設定して複合データ型は、します。 フィールドの長さの制限は、(2 つのコンポーネントの区切り記号を含む) の 3 つのコンポーネント内のデータが 180 小さいことを意味します。 ただし、3 つのデータ型の選択肢が指定されていません。つまり、すべてまたは一部のコンポーネントがあります。 さらに、ST および IS のデータ型では、ユーザーが定義されているため[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]通常定義されているサイトがあるために 3 つのコンポーネント間の長さの分散を意識することはできません。  
  
 これらおよびその他の複雑な問題により[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]フィールドの長さを検証しません。 ただしの長さ制限に個々 のコンポーネントとサブコンポーネント (データ型の単純な) での BizTalk エディターを使用してを適用して[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]します。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] これらの処理中に検証されます。  
  
## <a name="validation-of-batch-and-file-headerstrailers-are-affected-by-enabling-fragmentation"></a>断片化を有効にするとバッチとファイルのヘッダー/トレーラーの検証が影響を受ける  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] FHS3 フィールドには、断片化が有効になっているパーティが含まれている場合は、バッチとファイルのヘッダー/トレーラーを検証しません。  
  
## <a name="see-also"></a>参照  
 [既知の問題](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)