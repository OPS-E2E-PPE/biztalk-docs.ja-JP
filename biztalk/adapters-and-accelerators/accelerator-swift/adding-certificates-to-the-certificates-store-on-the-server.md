---
title: サーバー上の証明書ストアに証明書を追加する |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, adding to certificates store
- certificates store
ms.assetid: 075cfae8-dce7-46f7-9539-796f03229ea2
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94661568108e5a1cc05140a97c933fb8d00e3c67
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209570"
---
# <a name="adding-certificates-to-the-certificates-store-on-the-server"></a>サーバー上の証明書ストアに証明書を追加します。
サーバー コンピューター上の証明書 (ローカル コンピューター) ストアにその他のユーザー フォルダーに証明書を追加するのにには、次の手順を使用します。  
  
### <a name="to-add-certificates-to-the-certificate-store"></a>証明書ストアに証明書を追加するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk Accelerator 用 SWIFT**、順にクリック**BizTalk Accelerator for SWIFT の管理コンソール**です。  
  
    > [!NOTE]
    >  前の手順 (追加する証明書クライアントで証明書ストアを) 開く MMC ウィンドウをまだある場合は場合、は、この手順を使用できます。  
  
2.  管理コンソール ウィンドウで、**証明書 (ローカル コンピューター)** フォルダーの順に展開および**ほかの人**です。  
  
3.  右クリック**証明書**、 をポイント**すべてのタスク**、クリックして**インポート**です。  
  
4.  証明書のインポート ウィザードのページへようこそ、をクリックして**次**です。  
  
5.  ファイルのインポート ページで、をクリックして**参照**です。  
  
6.  [開く] ダイアログ ボックスで、証明書の選択を保存したファイルの場所に移動**すべてのファイル**の**ファイルの種類**、クリックして、インポートする証明書を選択**開いている**です。  
  
7.  ファイルのインポート ページで、をクリックして**次**です。  
  
8.  証明書ストア ページで、いることを確認**次のストアに証明書をすべてを配置**が選択されていることを確認**ほかの人**に表示される、**証明書ストア**ボックスをクリックして**次**です。  
  
9. 完了証明書のインポート ウィザードのページでをクリックして**完了**です。  
  
10. [正常なインポートを示す証明書のインポート ウィザード] ダイアログ ボックス、 **OK**です。  
  
11. メッセージの修復と新しい送信で使用するその他のすべての証明書には、手順 3. ~ 10. を繰り返します。