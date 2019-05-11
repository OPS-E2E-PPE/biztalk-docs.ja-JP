---
title: 保留メッセージの 16 進数の内容を表示することによってメッセージ検証エラーのトラブルシューティング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5cf14cd9-2d4b-43a3-9738-52bfd879e1e4
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 562caf377691e8bfcea5d05bba307e28859d7999
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65243122"
---
# <a name="troubleshooting-message-validation-failures-by-viewing-the-hexadecimal-contents-of-suspended-messages"></a>保留メッセージの 16 進数の内容を表示することによってメッセージ検証エラーのトラブルシューティング
検証エラーによりメッセージが中断の場合は、メッセージ部分の検証エラーの原因を特定する 16 進数形式で表示すると役立つ場合があります。 このトピックでは、中断されたメッセージの部分の 16 進数形式で表示する手順を示します。  
  
## <a name="use-the-message-details-dialog-box-to-view-message-parts"></a>メッセージの詳細 ダイアログ ボックスを使用してメッセージ部分の表示  
 メッセージ部分の 16 進数形式で表示する次の手順に従います。  
  
1.  使用して、**クエリ** タブで、BizTalk 管理コンソールを 1 つまたは複数の保留メッセージを含む結果セットを返します。 参照してください[メッセージを検索する方法](../core/how-to-search-for-messages.md)詳細についてはします。  
  
2.  表示する調査する保留中のメッセージをダブルクリックして、**メッセージの詳細**メッセージのダイアログ ボックス。  
  
3.  左側のウィンドウでメッセージ部分をクリックして、**メッセージの詳細**ダイアログ ボックスに、メッセージ部分を表示します。  
  
    > [!NOTE]
    >  メッセージには、0、1 つまたは複数のメッセージ部分があります。 メッセージがほとんどでは、"body"に呼び出される単一のメッセージ部分があります。  
  
4.  をクリックして、**バイナリ** タブの右側のウィンドウで、**メッセージの詳細**ダイアログ ボックスにメッセージ部分の 16 進数表現を表示します。  
  
5.  次のメッセージ部分の文字の 16 進数表現を確認します。  
  
    -   存在しないか無効のバイト オーダー マークします。 詳細については、バイト順はマークを参照してください[ http://go.microsoft.com/fwlink/?LinkId=196380](http://go.microsoft.com/fwlink/?LinkId=196380)します。  
  
    -   Unix と Windows での改行のエンコードの間の相違点。 Unix は、行の区切りを示すために、Windows が 16 進キャリッジ リターン (0 D) とラインフィード (0 a) の両方を使用するという改行を 16 進のラインフィード (0 a) を使用します。  
  
    -   メッセージ部分の無効な制御文字。 テキスト ビューで表示しないメッセージ部分の制御文字をバイナリのビューに表示されることがあります。  
  
    -   メッセージ部分の途中で無効な nul 文字には、メッセージ部分が切り捨てられる可能性があります。 Nul 文字は 16 進数 (00) として表されます。  
  
    -   無効な文字が位置指定フラット ファイル内のオフセットします。 位置指定フラット ファイルのデータのオフセットを表示するメッセージ部分の 16 進数表現を表示します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション、ポート、およびメッセージのエラーの調査](../core/investigating-orchestration-port-and-message-failures.md)