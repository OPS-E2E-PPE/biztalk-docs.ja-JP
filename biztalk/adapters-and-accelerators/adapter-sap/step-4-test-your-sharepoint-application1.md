---
title: 手順 4:テスト、SharePoint アプリケーション 1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f7ded5a5-88d5-40aa-814b-70bc0a7dcfa3
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 40160ef6e2e3a27a10a74779aa7eb8d282b2a30b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65372792"
---
# <a name="step-4-test-your-sharepoint-application"></a>手順 4:SharePoint アプリケーションをテストします。
![手順 4 の 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")  
  
 **所要時間:** 10 分  
  
 **目標:** SharePoint サイトで Web パーツを追加し、アプリケーションを作成した後は、SAP システムから一部のデータを取得することによってアプリケーションをテストする必要があります。 このトピックでは、アプリケーションを使用して、SAP システムからデータを取得する方法を説明します。  
  
## <a name="prerequisites"></a>前提条件  
  
-   ビジネス データを取得する適切な Web パーツが含まれる Web パーツ ページを作成する必要があります。 参照してください[手順 3。SAP からデータを取得する SharePoint アプリケーションを作成](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md)です。  
  
### <a name="to-test-the-sharepoint-application"></a>SharePoint アプリケーションをテストするには  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 クリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、順にクリックします**SharePoint 3.0 サーバーの全体管理**.  
  
2.  左側のナビゲーション ウィンドウで、アプリケーションを作成する SSP の名前をクリックします。  
  
3.  左側のウィンドウで次のようにクリックします。**すべてのサイト コンテンツの表示**します。 右側のウィンドウで次のようにクリックします。**フォーム テンプレート**します。  
  
4.  **フォーム カテゴリ**一覧で、 **Customer_SalesOrders**します。 Web パーツ ページを作成したときに、この名前を指定します。 次の図は、作成した Web パーツ ページを示します。  
  
     ![完成した Web パーツ ページ](../../adapters-and-accelerators/adapter-sap/media/3e9f22b1-8285-40f4-a67d-b51173c93671.gif "3e9f22b1-8285-40f4-a67d-b51173c93671")  
  
5.  検索文字列に基づいて顧客を検索します。 たとえば、"John E"で始まる顧客の検索します。 そのためには次を行います。  
  
    1.  最初のリストから、顧客の一覧] セクションで [ **CustomerName**します。  
  
    2.  2 番目の一覧からクリックして**で始まる**します。  
  
    3.  テキスト ボックスに「 **John E**します。  
  
    4.  をクリックして、**データの取得**リンクまたは ENTER キーを押します。 次の図は、検索条件に適合する SAP システムから取得したレコードを示します。  
  
         ![SAP システムからの結果を検索](../../adapters-and-accelerators/adapter-sap/media/c97e9e2c-0908-46af-9a54-8a4354847c47.gif "c97e9e2c-0908-46af-9a54-8a4354847c47")  
  
6.  存在する場合に、販売注文に関連付けられた、顧客とリスト内のすべての顧客の詳細を確認できますようになりました。 これを行うには、顧客数に対して、オプション ボタンをクリックします。 詳細、およびそれぞれの Web パーツで特定の顧客の販売注文を表示するページを更新します。  
  
     ![SharePoint に表示される SAP データ](../../adapters-and-accelerators/adapter-sap/media/29fc4a9e-facd-4455-bcfe-5f4d866b2dc7.gif "29fc4a9e-facd-4455-bcfe-5f4d866b2dc7")  
  
     顧客と関連付けられている販売注文の詳細が正しく表示されている場合は、このチュートリアルを正常に完了しました。 ない場合または不適切なデータが表示される、すべてのタスクが正常に実行するかどうかを確認する作業を慎重に確認します。  
  
## <a name="summary"></a>まとめ  
 このチュートリアルでは、SharePoint ポータルからアクセスする SAP アイテム用の WCF サービスを作成します。 SAP システムからデータを表示する Web パーツを作成する SharePoint ポータルにインポートされる SAP アイテム用のアプリケーション定義を作成します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1:SAP システムからのデータを SharePoint サイトに表示する](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)