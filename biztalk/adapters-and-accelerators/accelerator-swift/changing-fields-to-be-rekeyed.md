---
title: 変更するフィールドの変更 |Microsoft Docs
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
ms.openlocfilehash: 0468a692ecb7099920fca1c4714feb8ee9c1dfce
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378903"
---
# <a name="changing-fields-to-be-rekeyed"></a>変更するフィールドの変更
メッセージの修復ワークフローの検証手順で[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]検証ツールの再入力すると、または、そのデータを更新する必要がありますように、フィールドの数からデータを削除します。 RekeyVerify 内のフィールドをカスタマイズする[!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)]フォームを変更する必要があります。 ある MrsrXpathConfig.xml ファイルでこれを行う、 \<*ドライブ*\>: \Program Files\Microsoft BizTalk Accelerator for SWIFT\MRSR フォルダー。  
  
 MrsrXpathConfig.xml ファイルには、一連処理メッセージの種類のノードにはが含まれています。 各メッセージの種類のノードには、一連フィールドごとに 1 つのフィールド ノードにはが含まれています。 MrsrXpathConfig.xml をメモ帳などのテキスト エディターで開いてを追加または削除によって変更するフィールドを変更することができます、\<パス\>フィールドのノード。  
  
 \<パス\>ノードには、メッセージの種類と、フィールドのパスが含まれています。 たとえば、MT103 メッセージの入力アプリケーション ヘッダー ブロックの宛先パスのエントリは、次に示します。  
  
```  
<path>/*[local-name()='SWIFT_CATEGORY1_MT103_Interchange' and namespace-uri()'http://schemas.microsoft.com/BizTalk/Solutions/FinancialServices/SWIFT/Category1/MT103']/*[local-name()='SWIFTHeader' and namespace-uri=']'']/*[local-name()='ApplicationHeaderBlock_Input' and namespace-uri90='']/*[local-name()='DestinationAddress' and namespace-uri()='']</path>  
```  
  
 コピーおよび貼り付けて既存のエントリと関連するパスを変更することによって変更する新しいフィールドを追加する最も簡単になります。 たとえば、MT103 メッセージの値の日付銀行間決済金額 32 a のセクションでは、Date フィールドのキー更新を強制するには、上記のコードを次の 3 つの置換をください。 コードの残りの部分は同じです。  
  
|これで置き換えます|こっちと|  
|------------------|---------------|  
|`SWIFTHeader`|`SWIFT_CATEGORY1_MT103`|  
|`ApplicationHeaderBlock_Input`|`ValueDateCurrencyInterbankSettledAmount_32A`|  
|`DestinationAddress`|`Date`|  
  
 キー フィールドの更新の詳細については、次を参照してください。 [Message Repair and New Submission で特別な処理](../../adapters-and-accelerators/accelerator-swift/special-processing-in-message-repair-and-new-submission.md)します。