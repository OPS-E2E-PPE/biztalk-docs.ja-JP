---
title: 保留メッセージの 16 進数の内容を表示することによってメッセージの検証エラーのトラブルシューティング |Microsoft ドキュメント
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
ms.openlocfilehash: 2f7dc0f24a85f206831e3706bd03f2206aaa2c15
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279570"
---
# <a name="troubleshooting-message-validation-failures-by-viewing-the-hexadecimal-contents-of-suspended-messages"></a>保留メッセージの 16 進数コンテンツの確認によるメッセージ検証エラーのトラブルシューティング
メッセージが検証エラーにより保留された場合は、メッセージ部分を 16 進表現にして確認すると検証エラーの原因の特定に役立つことがあります。 このトピックでは、保留メッセージのメッセージ部分を 16 進表現で表示する手順について説明します。  
  
## <a name="use-the-message-details-dialog-box-to-view-message-parts"></a>[メッセージの詳細] ダイアログ ボックスを使用したメッセージ部分の表示  
 メッセージ部分を 16 進表現で表示するには、次の手順を実行します。  
  
1.  使用して、**クエリ** タブで、BizTalk 管理コンソールを 1 つまたは複数の保留メッセージを含む結果セットを返します。 参照してください[メッセージの検索方法](../core/how-to-search-for-messages.md)詳細についてはします。  
  
2.  表示を調査する保留中のメッセージをダブルクリックして、**メッセージの詳細**メッセージのダイアログ ボックス。  
  
3.  左側のウィンドウでメッセージ部分をクリックして、**メッセージの詳細**ダイアログ ボックスに、メッセージ部を表示します。  
  
    > [!NOTE]
    >  メッセージには、メッセージ部分を持たないものと 1 つまたは複数のメッセージ部分を持つものがあります。 "本文" と呼ばれるメッセージ部分を 1 つだけ持つメッセージがほとんどです。  
  
4.  クリックして、**バイナリ** タブの右側のペインで、**メッセージの詳細**ダイアログ ボックスに、メッセージ部分を 16 進表現を表示します。  
  
5.  メッセージ部分の文字を 16 進表現で表示して、次の点を確認します。  
  
    -   バイト オーダー マークの欠落または無効なバイト オーダー マーク。 詳細については、バイト順マークを参照してください[http://go.microsoft.com/fwlink/?LinkId=196380](http://go.microsoft.com/fwlink/?LinkId=196380)です。  
  
    -   UNIX と Windows での改行のエンコード方法の違い。 Unix では、改行を 16 進のラインフィード (0A) のみで表しますが、Windows では、16 進の復帰 (0D) とラインフィード (0A) の 2 つで表します。  
  
    -   メッセージ部分の無効な制御文字。 メッセージ部分の制御文字は、テキスト ビューでは表示されませんがバイナリ ビューでは表示できます。  
  
    -   メッセージ部分の途中の無効な Null 文字によるメッセージの切り捨て。 Null 文字は 16 進では 00 で表されます。  
  
    -   位置指定フラット ファイル内の無効な文字オフセット。 メッセージ部分を 16 進表現で表示すると、位置指定フラット ファイルのデータのオフセットを確認できます。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション、ポート、およびメッセージのエラーの調査](../core/investigating-orchestration-port-and-message-failures.md)