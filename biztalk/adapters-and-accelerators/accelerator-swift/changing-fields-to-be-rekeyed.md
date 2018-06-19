---
title: 再生成するフィールドの変更 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- rekeyed fields
- Message Repair and New Submission, modifying fields
- Message Repair and New Submission, rekeyed fields
ms.assetid: aaf353f7-0e43-403e-b72a-88e5dd07f4ac
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04693bf4c4d441487a3ce38f886bc680b1db368b
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25964496"
---
# <a name="changing-fields-to-be-rekeyed"></a>再生成するフィールドを変更します。
メッセージの修復ワークフローの検証手順で[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ように、検証側は必要がありますを再入力したり鍵更新、そのデータ フィールドの数からそのデータを削除します。 RekeyVerify 内のどのフィールドをカスタマイズする[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームを再生成する必要があります。 ある MrsrXpathConfig.xml ファイルで行う、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\MRSR フォルダーです。  
  
 MrsrXpathConfig.xml ファイルには、一連処理されたメッセージの種類のノードにはが含まれています。 メッセージの種類の各ノードには、一連フィールドごとに 1 つのフィールド ノードにはが含まれています。 メモ帳などのテキスト エディターで MrsrXpathConfig.xml を開いて、追加または削除して再生成するのにフィールドを変更することができます、\<パス\>フィールドのノードです。  
  
 \<パス\>ノードには、メッセージの種類と、フィールドのパスが含まれています。 たとえば、MT103 メッセージの入力アプリケーション ヘッダー ブロック先のパスのエントリは、次に示します。  
  
```  
<path>/*[local-name()='SWIFT_CATEGORY1_MT103_Interchange' and namespace-uri()'http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/Category1/MT103']/*[local-name()='SWIFTHeader' and namespace-uri=']'']/*[local-name()='ApplicationHeaderBlock_Input' and namespace-uri90='']/*[local-name()='DestinationAddress' and namespace-uri()='']</path>  
```  
  
 方が簡単にコピーして貼り付けなくても、既存のエントリでは、関連するパスを変更することに再生成する新しいフィールドを追加します。 など、日付、日付通貨銀行間決済金額 32 a のセクションでフィールド MT103 メッセージのキー更新を強制するには、上記のコードを次の 3 つの置換を確認します。 コードの残りの部分は変わりません。  
  
|これで置き換えます|こっちと|  
|------------------|---------------|  
|`SWIFTHeader`|`SWIFT_CATEGORY1_MT103`|  
|`ApplicationHeaderBlock_Input`|`ValueDateCurrencyInterbankSettledAmount_32A`|  
|`DestinationAddress`|`Date`|  
  
 フィールドのキー更新の詳細については、次を参照してください。 [Message Repair and New Submission の特別な処理](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md)です。