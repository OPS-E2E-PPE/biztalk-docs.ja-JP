---
title: '手順 4: テスト、SharePoint アプリケーションの 1 |Microsoft ドキュメント'
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
ms.openlocfilehash: 9b8be51df02bd9796b41201c0495758c281e8f14
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216634"
---
# <a name="step-4-test-your-sharepoint-application"></a>手順 4: SharePoint アプリケーションをテストします。
![4 のステップ 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")  
  
 **所要時間:** 10 分  
  
 **目標:** SharePoint サイトに Web パーツを追加するいるし、アプリケーションを作成する必要がありますアプリケーションをテストする SAP システムから一部のデータを取得しています。 このトピックでは、アプリケーションを使用して SAP システムからデータを取得する方法について説明します。  
  
## <a name="prerequisites"></a>前提条件  
  
-   ビジネス データを取得する適切な Web パーツが含まれる Web パーツ ページを作成する必要があります。 参照してください[手順 3: SAP からデータを取得する SharePoint アプリケーションを作成](../../adapters-and-accelerators/adapter-sap/step-3-create-a-sharepoint-application-to-retrieve-data-from-sap.md)です。  
  
### <a name="to-test-the-sharepoint-application"></a>SharePoint アプリケーションをテストするには  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.  
  
2.  左側のナビゲーション ウィンドウで、アプリケーションを作成する、SSP の名前をクリックします。  
  
3.  左側のウィンドウでをクリックして**すべてのサイト コンテンツの表示**です。 右側のウィンドウでをクリックして**フォーム テンプレート**です。  
  
4.  **フォーム カテゴリ**一覧で、クリックして**Customer_SalesOrders**です。 Web パーツ ページを作成したときに、この名前を指定します。 次の図は、作成した Web パーツ ページを示します。  
  
     ![完成した Web パーツ ページ](../../adapters-and-accelerators/adapter-sap/media/3e9f22b1-8285-40f4-a67d-b51173c93671.gif "3e9f22b1-8285-40f4-a67d-b51173c93671")  
  
5.  検索文字列に基づいて顧客を検索します。 たとえば、"John E"で始まる顧客を検索します。 そのためには次を行います。  
  
    1.  最初のリストから、顧客の一覧のセクションで  **CustomerName**です。  
  
    2.  2 番目の一覧からクリックして**で始まる**です。  
  
    3.  テキスト ボックスで、次のように入力します。 **John E**です。  
  
    4.  クリックして、**データの取得**リンクまたは ENTER キーを押します。 次の図は、検索条件に適合する SAP システムから取得したレコードを示します。  
  
         ![SAP システムからの結果を検索](../../adapters-and-accelerators/adapter-sap/media/c97e9e2c-0908-46af-9a54-8a4354847c47.gif "c97e9e2c-0908-46af-9a54-8a4354847c47")  
  
6.  リスト内のすべての顧客の詳細を表示できるようになりましたし、販売注文に関連付けられている、顧客、存在する場合。 これを行うには、顧客番号に対して、オプション ボタンをクリックします。 詳細とそれぞれの Web パーツで特定の顧客の販売注文を表示するページを更新します。  
  
     ![SharePoint に表示される SAP データ](../../adapters-and-accelerators/adapter-sap/media/29fc4a9e-facd-4455-bcfe-5f4d866b2dc7.gif "29fc4a9e-facd-4455-bcfe-5f4d866b2dc7")  
  
     顧客と関連する販売注文の詳細が正しく表示されている場合は、このチュートリアルを正常に完了しました。 ない場合、または不適切なデータが表示されたら、すべてのタスクが正常に実行するかどうかを確認する作業を慎重に確認します。  
  
## <a name="summary"></a>概要  
 このチュートリアルでは、SharePoint ポータルからアクセスする SAP 成果物のための WCF サービスを作成します。 SAP システムからデータを表示する Web パーツを作成する SharePoint ポータルにインポートされている SAP 成果物のためのアプリケーション定義を作成します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1: SharePoint サイト上の SAP システムからのデータの表示](../../adapters-and-accelerators/adapter-sap/tutorial-1-presenting-data-from-an-sap-system-on-a-sharepoint-site.md)