---
title: "手順 4: テスト SharePoint アプリケーションの Siebel アダプターと |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ec1392fa-fdc1-42be-b4dc-75a55d8fa400
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 85cebcafcdf768686ed3f7382a0838db5062d96b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-test-your-sharepoint-application-with-the-siebel-adapter"></a>手順 4: Siebel アダプターと、SharePoint アプリケーションをテストします。
![4 のステップ 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")  
  
 **所要時間:** 5 分です。  
  
 **目標:** SharePoint サイトに Web パーツを追加するいるし、アプリケーションを作成する必要がありますアプリケーションをテストする Siebel システムの一部のデータを取得しています。 このセクションでは、アプリケーションを使用して、Siebel システムからデータを取得する方法の指示を提供します。  
  
## <a name="prerequisites"></a>前提条件  
 ビジネス データを取得する適切な Web パーツを含む Web パーツ ページを作成する必要があります。 参照してください[手順 3: Siebel からデータを取得する SharePoint アプリケーションを作成](../../adapters-and-accelerators/adapter-siebel/step-3-create-a-sharepoint-application-to-retrieve-data-from-siebel.md)です。  
  
### <a name="to-test-the-sharepoint-application"></a>SharePoint アプリケーションをテストするには  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.  
  
2.  左側のナビゲーション ウィンドウで、アプリケーションを作成する、SSP の名前をクリックします。  
  
3.  左側のウィンドウでをクリックして**すべてのサイト コンテンツの表示**です。 右側のウィンドウからをクリックして**フォーム テンプレート**です。  
  
4.  **フォーム カテゴリ**一覧で、クリックして**Siebel アカウント**です。 Web パーツ ページを作成中には、この名前を指定します。 次の図は、作成した Web パーツ ページを示します。  
  
     ![完成した Web パーツ ページ](../../adapters-and-accelerators/adapter-siebel/media/a0bfe7af-0246-4f0b-aa0d-0ee084456003.gif "a0bfe7af-0246-4f0b-aa0d-0ee084456003")  
  
5.  検索文字列に基づくアカウント ビジネス コンポーネントのクエリを実行します。 たとえば、検索式を指定`[Name] LIKE ‘W*’`です。 そのためには次を行います。  
  
    1.  **アカウント一覧**セクションの最初のリストから選択**SearchExpression**、し、**と等しい**です。  
  
    2.  テキスト フィールドに「`[Name] LIKE ‘W*’`です。  
  
    3.  をクリックして**データの取得**リンク、または ENTER キーを押します。 次の図は、検索条件に適合する Siebel システムから取得したレコードを示します。  
  
         ![Siebel システムからの結果を検索](../../adapters-and-accelerators/adapter-siebel/media/6c4721ac-c7bc-4626-9ee0-55cf322026cf.gif "6c4721ac-c7bc-4626-9ee0-55cf322026cf")  
  
## <a name="see-also"></a>参照  
 [チュートリアル 1: SharePoint サイト上の Siebel システムからのデータの表示](../../adapters-and-accelerators/adapter-siebel/tutorial-1-presenting-data-from-a-siebel-system-on-a-sharepoint-site.md)