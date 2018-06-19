---
title: 検証の既知の問題 |Microsoft ドキュメント
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
ms.openlocfilehash: 69400c5196b31a53d49055e500356c7ce3430e58
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207042"
---
# <a name="validation-known-issues"></a>検証に関する既知の問題
このセクションには、検証エラーを回避するために役立つ有用な情報が含まれています。  
  
## <a name="disabling-xml-validation"></a>XML 検証を無効にします。  
 「本文の検証セグメント」フラグ[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]エクスプ ローラーの構成が XML 本文の検証を制御し、予期しない区切り記号や末尾の区切り記号の検証には含まれません。 メッセージが適切な区切り記号を持たない場合、メッセージを正常に解析できません。 メッセージを正常に解析できない場合[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]中級者向けの有効な XML を生成することはできません。 「本文セグメントの検証」フラグを無効にするは、次が得られます。  
  
1.  空の必須フィールドです。  
  
2.  データ型は検証されません。  
  
3.  セグメント構造の検証は行われません (セグメントの順序は検証されません)。  
  
## <a name="v2xml-acks-with-multiple-errors-will-fail-validation"></a>V2 です。複数のエラーのある XML Ack は検証に失敗します。  
 着信 V2 の場合。XML メッセージには、1 つ以上のエラーが含まれています、 [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] BizTalk Accelerator 用 HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) パーサーが、V2 を生成する可能性があります。エラー フィールドに 1 つ以上のエラーのため、XML の確認 (ACK)。 このような V2 です。HL7 標準を指定して、パーサーが、V2 で 1 つだけのエラーを報告できるので、XML ACK では、検証は失敗します。XML ACK エラー フィールドです。  
  
## <a name="two-parsing-errors-are-logged-when-messages-in-the-batch-inbatch-out-scenario-contain-validation-errors"></a>2 つの解析エラーがログに記録ときに、バッチ内のメッセージのバッチをシナリオに検証エラーを含める/  
 バッチ内の最初のメッセージのバッチをシナリオ (複数のメッセージがバッチ ヘッダーのないバッチ) には、検証エラーが含まれています/[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]イベント ログに 2 つのエラーをログに記録します。 最初のエラーが、バッチの最初のメッセージに関連し、メッセージの残りの部分に関連する 2 番目のエラーです。  
  
## <a name="restrictions-in-validating-field-length"></a>フィールドの長さの検証の制限事項  
 HL7 の複雑なデータ型は、のコンポーネントとサブコンポーネントで構成に関連付けられているフィールドです。 HL7 ルールは、長さとフィールド レベルとコンポーネントまたはサブコンポーネント レベルではなくオプションかどうかを指定します。 たとえば、V2.4 HL7 は HD データ型と 180 文字の最大長である MSH3 を制御します。 HD は、HD1 セットは、ST、として HD2 セット id。 として hd3 はどれも設定と、複合データ型は、します。 フィールドの長さの制限は、(2 つのコンポーネントの区切り記号を含む)、3 つのコンポーネント内のデータが 180 小さいことを意味します。 ただし、3 つのデータ型の選択肢が指定されていません。つまり、すべてまたは一部のコンポーネントがあります。 さらに、ST および IS データ型は、ユーザー定義し、したがって[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]それらが定義されているサイトでは通常、3 つのコンポーネント間で時間の分布を認識することはできません。  
  
 これらおよびその他の複雑な問題が原因[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]フィールドの長さは検証されません。 ただし、制限を適用できます長さ個々 のコンポーネントとサブコンポーネントでのデータ型の単純な) BizTalk エディターを使用した[!INCLUDE[btsVStudioNoVersion](../../includes/btsvstudionoversion-md.md)]です。 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]これらの処理中に検証します。  
  
## <a name="validation-of-batch-and-file-headerstrailers-are-affected-by-enabling-fragmentation"></a>断片化を有効にするとバッチとファイルのヘッダー/トレーラーの検証が影響を受ける  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]FHS3 フィールドには、断片化が有効になっているは、パーティが含まれている場合は、バッチとファイルのヘッダー/トレーラーを検証しません。  
  
## <a name="see-also"></a>参照  
 [既知の問題](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)