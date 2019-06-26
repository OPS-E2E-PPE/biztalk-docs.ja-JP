---
title: 数値検証のオフセットを設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- amounts, validating
- validating, amounts
- amounts, offsets
- offsets
ms.assetid: 39d5510c-52e6-4fd9-9632-582b508f04d7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b194445499f2506b1dcb8309cb20f4aa17e6ca83
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377044"
---
# <a name="setting-offsets-for-amount-validation"></a>数値検証のオフセットを設定
メッセージの種類、MT102 MT103、および MT103PLUS 金額のフィールドの使用に関する規則は、それぞれの検証ポリシーの規則によって検証されます。 金額のフィールドは、厳密に一致することができます。 または金額の範囲内に検証することができます。  
  
 範囲内での検証を有効にするには、関連する検証ポリシーでのメソッド呼び出しで、オフセットの比率を指定します。 たとえば、フィールドに設定した金額が 100 で、オフセットの率が 10% の場合、有効な金額は、110 では、包括的に 90 から任意の値をなります。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] MT102、MT102PLUS、および MT103 メッセージの種類には、このサポートを提供します。  
  
 オフセットの比率がいずれかで指定された、 **IsValidSettlementAmount**または**IsValidInterbankSettledAmount**検証ポリシー内のメソッド。 **IsValidSettlementAmount** MT102 および MT102PLUS メッセージの量のフィールドの使用量のルールを実装します。 **IsValidInterbankSettledAmount** MT103 メッセージの量のフィールドの使用量のルールを実装します。 これらのメソッドのいずれかの 10 番目の引数である OffsetPercent 引数には、オフセットの比率を指定します。  
  
 オフセットのパーセントは設定すると、次のフィールドに適用されます。  
  
|メッセージ型|フィールドのオフセットを使用して検証|  
|------------------|-----------------------------------|  
|MT102 または MT102PLUS|32<br /><br /> 33B|  
|MT103|シーケンス C、19<br /><br /> 31 a、C のシーケンス<br /><br /> 72 G|  
  
### <a name="to-set-an-offset-percentage"></a>オフセットの率を設定するには  
  
1.  メモ帳などのテキスト エディターを開きます。  
  
2.  エディターでは、オフセットの比率を設定するメッセージの検証ポリシーの場所を参照します。 たとえば、見つかりますメッセージの検証ポリシー MT103_Validation_Policy.xml、MT103 メッセージの種類で *\<ドライブ\>* : Microsoft BizTalk Accelerator for SWIFT \Program Files\ \<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT-SRG\<バージョン\>\Category 1\MT103 します。 検証ポリシーを開きます。  
  
3.  ポリシーでは、検索 IsValidSettlementAmount MT102 および MT102PLUS メッセージまたは IsValidInterbankSettledAmount MT103 メッセージ。  
  
4.  10 番目の引数には、カウント ダウンします。 引数のオフセットの割合を入力します。  
  
5.  ファイルを保存し、エディターを閉じます。