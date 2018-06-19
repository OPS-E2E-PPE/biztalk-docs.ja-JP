---
title: 送信ポートのフィルター式を設定 |Microsoft ドキュメント
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
ms.openlocfilehash: b94497f4e1412f81c36df3195994aafa32ecc451
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22206082"
---
# <a name="setting-filter-expressions-on-send-ports"></a>送信ポートのフィルター式を設定
ポートの送信を制御する送信ポートにフィルター式のコンテキスト プロパティを設定します。 プロパティのフィルター処理する方法の柔軟性を提供する演算子の数が、フィルター式を設定することができます (より大きいより優れたまたは同じか、少ないよりと小さい、等しいかどうか、存在よりまたは等しい)。  
  
### <a name="to-set-the-filter-expression-on-a-send-port"></a>送信ポートにフィルター式を設定するには  
  
1.  BizTalk Server 管理コンソールで、展開**BizTalk Server 管理コンソール**、 **BizTalk グループ**、**アプリケーション**、および**BizTalk アプリケーション1** (または別のアプリケーション)。 をクリックして**送信ポート**です。  
  
2.  では、フィルター式を設定し、をクリックする送信ポートを右クリックして**プロパティ**です。  
  
3.  送信ポートのプロパティ ダイアログ ボックスのコンソール ツリーで、クリックして**フィルター**です。  
  
4.  内のテキスト ボックスをクリックして、**プロパティ**列からコンテキスト プロパティを選択し、**プロパティ**ドロップダウン リスト。  
  
5.  クリックして、**演算子** ボックスに、プロパティの行と、プロパティの演算子をドロップダウン リストから選択します。  
  
6.  クリックして、**値** ボックスに、プロパティの行と値の式を入力します。  
  
7.  フィルター式に対して別の句を追加する必要がある場合にクリックして、 **Group By**  ボックスに、プロパティの行と選択**と**または**または**の関係を判断する、句。  
  
8.  手順 4 ~ 6 を別のフィルター句を追加します。  
  
9. フィルター式でが正しいこと、ウィンドウの下部にあることを確認、**フィルター**ウィンドウです。  
  
10. すべてのフィルター句を追加したら、をクリックして**OK**です。  
  
## <a name="see-also"></a>参照  
 [HL7 メッセージの処理](../../adapters-and-accelerators/accelerator-hl7/processing-hl7-messages.md)   
 [コンテキスト プロパティを使用します。](../../adapters-and-accelerators/accelerator-hl7/using-context-properties.md)