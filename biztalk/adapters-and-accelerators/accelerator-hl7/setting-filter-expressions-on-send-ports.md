---
title: 送信ポートでのフィルター式の設定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send ports, context properties
- filtering, send ports
- send ports, filtering
- context properties, send ports
- context properties, filtering
- filtering, context properties
ms.assetid: 48c7c83b-9464-4ed9-bd8d-cf5b75e16702
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ab5fcc0e4245599dfffb29f6f5690707df325c04
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65291569"
---
# <a name="setting-filter-expressions-on-send-ports"></a>送信ポートのフィルター式の設定
ポートの送信を制御する送信ポートでフィルター式のコンテキスト プロパティを設定します。 フィルター式を設定するにはさまざまなプロパティをフィルター処理する方法の柔軟性を提供する演算子 (等値演算子または非等値、存在するより大きいより大きいまたは等しい、未満よりと小さい以上)。  
  
### <a name="to-set-the-filter-expression-on-a-send-port"></a>送信ポートでフィルター式を設定するには  
  
1.  BizTalk Server 管理コンソールで  **BizTalk Server 管理**、 **BizTalk グループ**、**アプリケーション**、および**BizTalk アプリケーション1** (または別のアプリケーション)。 クリックして**送信ポート**します。  
  
2.  フィルター式を設定し、クリックする送信ポートを右クリックして**プロパティ**します。  
  
3.  送信ポートのプロパティ ダイアログ ボックスのコンソール ツリーで、クリックして**フィルター**します。  
  
4.  テキスト ボックスをクリックして、**プロパティ**列からコンテキスト プロパティをクリックして、**プロパティ**ドロップダウン リスト。  
  
5.  をクリックして、**演算子**プロパティに、行のボックスし、ドロップダウン リストから、プロパティの演算子を選択します。  
  
6.  をクリックして、**値** ボックスに、プロパティの行と値の式を入力します。  
  
7.  フィルター式に対して別の句を追加する必要がある場合にクリックして、 **Group By**  ボックスに、プロパティの行と選択**と**または**または**の関係を判断する、句。  
  
8.  手順 4 ~ 6 をもう 1 つのフィルター句を追加します。  
  
9. フィルター式が、ウィンドウの下部で正しいことを確認、**フィルター**ウィンドウ。  
  
10. すべてのフィルター句を追加したら、クリックして**OK**します。  
  
## <a name="see-also"></a>参照  
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [コンテキスト プロパティの使用](../../adapters-and-accelerators/accelerator-hl7/using-context-properties.md)