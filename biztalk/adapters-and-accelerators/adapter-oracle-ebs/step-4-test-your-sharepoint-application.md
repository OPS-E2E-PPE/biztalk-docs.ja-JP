---
title: "手順 4: SharePoint アプリケーションのテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a859044e-a28e-477e-a20b-f9bb3c9f7405
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 427235d27e4e783111ccdb60f799c228737cd008
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="step-4-test-your-sharepoint-application"></a>手順 4: SharePoint アプリケーションをテストします。
![4 のステップ 4](../../adapters-and-accelerators/adapter-oracle-ebs/media/step-4of4.gif "Step_4of4")  
  
 **所要時間:** 10 分  
  
 **目標:** SharePoint サイトに Web パーツを追加するいるし、アプリケーションを作成する必要がありますアプリケーションをテストする Oracle E-business Suite から一部のデータを取得しています。 このトピックでは、アプリケーションを使用して、Oracle E-business Suite からデータを取得する方法について説明します。  
  
## <a name="prerequisites"></a>前提条件  
 ビジネス データを取得する適切な Web パーツが含まれる Web パーツ ページを作成する必要があります。 参照してください[手順 3: Oracle E-business Suite からデータを取得する SharePoint アプリケーションを作成](../../adapters-and-accelerators/adapter-oracle-ebs/step-3-create-a-sharepoint-application-to-retrieve-data-from-oracle-ebs.md)です。  
  
### <a name="scenario-1-to-test-the-sharepoint-application-created-using-business-data-list-web-part"></a>シナリオ 1: この SharePoint アプリケーションをテストするには、ビジネス データ一覧 Web パーツを使用して作成されました。  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.  
  
2.  左側のナビゲーション ウィンドウで、アプリケーションを作成する、SSP の名前をクリックします。  
  
3.  左側のウィンドウでをクリックして**すべてのサイト コンテンツの表示**です。 右側のウィンドウでをクリックして**フォーム テンプレート**です。  
  
4.  **フォーム カテゴリ**一覧で、クリックして**MS_SAMPLE_EMPLOYEE**です。 Web パーツ ページを作成したときに、この名前を指定した[シナリオ 1: ビジネス データ一覧 web パーツを使用してデータを表示](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-1-display-data-using-business-data-list-web-part.md)です。  
  
5.  検索文字列に基づく従業員を検索します。 たとえば、すべての従業員を検索する次のように入力します。  **%**  、テキスト ボックスに**データの取得**です。 次の図は、Oracle E-business Suite から取得したレコードを示しています。  
  
     ![検索結果](../../adapters-and-accelerators/adapter-oracle-ebs/media/bdc-result.gif "BDC_Result")  
  
6.  名または姓を入力して特定の従業員を検索することもできます。  
  
    -   最初の名前を使用してを検索するには、初期の文字を入力、従業員名に続けて、  **%** 検索条件に一致するすべての従業員のレコードを返す記号。  
  
    -   使用して、姓と名を検索するには、次のように入力します。  **%** 従業員の姓を続けています。  
  
    > [!NOTE]
    >  検索文字列では大文字小文字を区別します。  
  
     ![従業員の名で検索](../../adapters-and-accelerators/adapter-oracle-ebs/media/b5044c4d-31ec-46d8-b02c-3b26bfe8178e.gif "b5044c4d-31ec-46d8-b02c-3b26bfe8178e")  
  
### <a name="scenario-2-to-test-the-sharepoint-application-created-to-perform-a-full-text-search"></a>シナリオ 2: SharePoint アプリケーションのテストを作成するフルテキスト検索を実行  
  
1.  SharePoint 3.0 サーバーの全体管理を開始します。 をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office Server**、クリックして**SharePoint 3.0 サーバーの全体管理**.  
  
2.  左側のナビゲーション ウィンドウで、アプリケーションを作成する、SSP の名前をクリックします。  
  
3.  左側のウィンドウでをクリックして**すべてのサイト コンテンツの表示**です。 右側のウィンドウでをクリックして**フォーム テンプレート**です。  
  
4.  **フォーム カテゴリ**一覧で、クリックして**MS_SAMPLE_EMPLOYEE_Search**です。 Web パーツ ページを作成したときに、この名前を指定した[シナリオ 2: 検索ボックス Web パーツを使用して検索を実行](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)で[シナリオ 2: 検索ボックス Web パーツを使用して検索を実行](../../adapters-and-accelerators/adapter-oracle-ebs/scenario-2-search-using-the-search-box-web-part.md)です。  
  
5.  MS_SAMPLE_EMPLOYEE_Search ページには、MS_SAMPLE EMPLOYEE テーブルのフルテキスト検索を実行することができます、検索ボックスが表示されます。 たとえば、ニューヨークに住んでいるすべての従業員を検索する場合は、「`New York`で検索ボックス、および ENTER キーを押します。  
  
     ![検索パラメーターの指定](../../adapters-and-accelerators/adapter-oracle-ebs/media/34-search-result.gif "34 _ search_result")  
  
6.  検索結果ページが表示されます。 各一致するレコードは、検索結果 ページでリンクとして表示されます。  
  
     ![検索結果](../../adapters-and-accelerators/adapter-oracle-ebs/media/05cc6fdc-8c9f-4312-8579-ef1753d02c63.gif "05cc6fdc-8c9f-4312-8579-ef1753d02c63")  
  
7.  対応する従業員レコードを表示する検索結果内のリンクをクリックします。  
  
     ![詳細な従業員レコード](../../adapters-and-accelerators/adapter-oracle-ebs/media/36-search-result2.gif "36 _ search_result2")  
  
## <a name="summary"></a>概要  
 このチュートリアルでは、SharePoint ポータルからアクセスする Oracle E-business Suite の成果物のための WCF サービスを作成します。 Oracle E-business Suite 成果物のための存在し、Oracle E-business Suite でデータを検索する Web パーツを作成する SharePoint ポータルにインポートされているアプリケーション定義を作成します。  
  
## <a name="see-also"></a>参照  
 [チュートリアル: SharePoint サイト上の Oracle E-business Suite からデータを表示します。](../../adapters-and-accelerators/adapter-oracle-ebs/tutorial-present-data-from-oracle-e-business-suite-on-a-sharepoint-site.md)