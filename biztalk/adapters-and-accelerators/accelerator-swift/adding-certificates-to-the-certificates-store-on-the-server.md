---
title: サーバーの証明書ストアに証明書の追加 |Microsoft Docs
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
ms.openlocfilehash: 973dc2caa5fd3950a8e1bebb74cf2c3e13806d60
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378880"
---
# <a name="adding-certificates-to-the-certificates-store-on-the-server"></a>サーバーの証明書ストアに証明書を追加します。
次の手順を使用すると、サーバー コンピューター (ローカル コンピューター) の証明書ストア内の他のユーザー フォルダーに証明書を追加できます。  
  
### <a name="to-add-certificates-to-the-certificate-store"></a>証明書ストアに証明書を追加するには  
  
1.  クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft BizTalk Accelerator for SWIFT**、順にクリックします**BizTalk Accelerator for SWIFT の管理コンソール**します。  
  
    > [!NOTE]
    >  前の手順 (追加の証明書クライアントで証明書ストアに) から開く MMC ウィンドウをまだ場合は、この手順で使用できます。  
  
2.  管理コンソール ウィンドウで、**証明書 (ローカル コンピューター)** フォルダーを順に展開**その他のユーザー**します。  
  
3.  右クリック**証明書**、 をポイント**すべてのタスク**、 をクリックし、**インポート**します。  
  
4.  証明書のインポート ウィザードのページへようこそ、をクリックして**次**します。  
  
5.  ファイルのインポート ページで、をクリックして**参照**します。  
  
6.  [開く] ダイアログ ボックスで、証明書の選択を保存したファイルの場所に移動します**すべてのファイル**の**ファイルの種類**、クリックして、インポートする証明書を選択 **。開いている**します。  
  
7.  ファイルのインポート ページで、をクリックして**次**します。  
  
8.  証明書ストア ページで、ことを確認します**次のストアに証明書をすべてを配置**が選択されていることを確認します**その他のユーザー**に表示される、**証明書ストア**ボックスをクリックして**次**します。  
  
9. 完了証明書のインポート ウィザード ページで、をクリックして**完了**します。  
  
10. [インポートに成功を示す証明書のインポート ウィザード] ダイアログ ボックス、 **OK**します。  
  
11. 手順 3 ~ 10 メッセージの修復と新しい送信で使用するその他のすべての証明書を繰り返します。