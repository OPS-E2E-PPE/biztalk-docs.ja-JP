---
title: 時間検証のためのオフセットを設定 |Microsoft ドキュメント
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
ms.openlocfilehash: 7cfae474407daa7dd3c0b95db3fed076a581cf1c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
ms.locfileid: "25961256"
---
# <a name="setting-offsets-for-amount-validation"></a>時間検証のためのオフセットを設定します。
メッセージ型 MT102、MT103、や MT103PLUS 金額のフィールドの使用に関する規則は、それぞれの検証ポリシーのルールによって検証されます。 金額のフィールドは、厳密に一致することができます。 または金額の範囲内であることを検証することができます。  
  
 範囲内での検証を有効にするには、関連する検証ポリシーでメソッドの呼び出しでオフセットの割合を指定します。 フィールドに設定した金額が 100、オフセットの割合が 10% 場合は、たとえば、有効な金額では、110、包括的に 90 から任意の値になります。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]MT102、MT102PLUS、および MT103 メッセージの種類には、このサポートを提供します。  
  
 オフセットの割合がいずれかで指定された、 **IsValidSettlementAmount**または**IsValidInterbankSettledAmount**検証ポリシー内のメソッドです。 **IsValidSettlementAmount** MT102 および MT102PLUS メッセージの量のフィールドの使用量のルールを実装するメソッド。 **IsValidInterbankSettledAmount** MT103 メッセージの量のフィールドの使用量のルールを実装するメソッド。 オフセットの割合を指定するには、これらのメソッドのいずれかの 10 番目の引数である OffsetPercent 引数にします。  
  
 オフセットのパーセントは設定すると、次のフィールドに適用されます。  
  
|メッセージ型|フィールドのオフセットを使用して検証|  
|------------------|-----------------------------------|  
|MT102 または MT102PLUS|32<br /><br /> 33B|  
|MT103|シーケンス C、19<br /><br /> 31A、シーケンス C<br /><br /> 72 G|  
  
### <a name="to-set-an-offset-percentage"></a>オフセットの割合を設定するには  
  
1.  メモ帳などのテキスト エディターを開きます。  
  
2.  エディターでは、オフセットの割合を設定するメッセージの検証ポリシーの場所を参照します。 たとえば、メッセージ検証ポリシー用あります MT103 メッセージの種類、MT103_Validation_Policy.xml で*\<ドライブ\>*: \Program Files\ Microsoft BizTalk Accelerator 用 SWIFT \<バージョン\>メッセージ Pack\SWIFT Messages\A4SWIFT SRG\<バージョン\>\Category 1\MT103 です。 検証ポリシーを開きます。  
  
3.  ポリシーで IsValidSettlementAmount で MT102 および MT102PLUS メッセージまたは IsValidInterbankSettledAmount MT103 メッセージ検索します。  
  
4.  10 番目の引数には、カウント ダウンします。 引数のオフセットの割合を入力します。  
  
5.  ファイルを保存し、エディターを閉じます。