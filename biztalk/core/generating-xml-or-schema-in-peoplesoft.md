---
title: "PeopleSoft で XML またはスキーマを生成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- generating schemas
- schemas, generating
- generating XML
- XML, generating
ms.assetid: adfe2936-0dc2-42d2-b26a-718f8cc57eff
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1a7fbd164f7c0d380f6ee0c0fda59098203f7585
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="generating-xml-or-schema-in-peoplesoft"></a>PeopleSoft での XML またはスキーマの生成
次の手順では、PeopleSoft Enterprise を使用して、XML ファイルを作成し、PeopleSoft イベントをトリガーする方法について説明します。 これを行うには、PeopleSoft 環境の一部を変更します。 この変更によって XML ファイルがアクティブ化され、オーケストレーションで監視対象に設定したファイル フォルダーに送信されます。 その後、BizTalk Server で、XML をインポートしてスキーマを生成します。  
  
> [!NOTE]
>  この場所を MSEXTERNAL ノードと関連付けると、"Location Value" が変更された場合に、XML ドキュメントが生成され、イベントがトリガーされます。 オーケストレーションの参加および開始後は、PeopleSoft の画面から [LOCATION] 画面に移動できます。 "Location Value" を変更し、その変更を保存すると、対応する XML が \out ディレクトリに現れます。  
  
### <a name="to-generate-xml-or-schema-in-peoplesoft"></a>PeopleSoft で XML またはスキーマを生成するには  
  
1.  PeopleSoft アプリケーションをポイント**Set up Financials**、 をポイント**Supply Chain**、 をポイント**共通定義**、 をポイント**場所**、し、**場所**です。  
  
2.  **場所**画面で、次の情報を入力します。  
  
    -   **ID:**入力**共有**です。  
  
    -   **Location Code:**で始まるコードを入力`WKLOC`です。  
  
     ![](../core/media/psadapter-18-task-sharesearch.gif "PSAdapter_18_Task_ShareSearch")  
  
3.  をクリックして**検索**、順にクリック**Correct History**に画面を記述する**編集**モード。  
  
     ![](../core/media/psadapter-19-task-correcthistory.gif "PSAdapter_19_Task_CorrectHistory")  
  
4.  クリックして、画面上のフィールドに変更を加える**保存**です。  
  
5.  をポイント**PeopleTools**、 をポイント**Integration Broker**、 をポイント**モニター**、し、 **Monitor Message**です。  
  
     ![](../core/media/psadapter-20-task-monitormessage.gif "PSAdapter_20_Task_MonitorMessage")  
  
6.  確認して**チャネルの種類**は**メッセージ インスタンス**、クリックして**更新**です。  
  
7.  **実行** 列番号をクリックします。  
  
8.  一覧の一番下までスクロールし、**詳細**リンクを**LOCATION_SYNC**メッセージ。  
  
     ![](../core/media/psadapter-21-task-detailslink.gif "PSAdapter_21_Task_DetailsLink")  
  
9. をクリックして**XML を表示**上、 **MSEXTERNAL**ノード。  
  
     ![](../core/media/psadapter-22-task-viewxml.gif "PSAdapter_22_Task_ViewXML")  
  
     XML の内容をコピーし、BizTalk Server プロジェクトからアクセスできるファイルに貼り付けます。  
  
     ![](../core/media/psadapter-23-task-xmlresult.gif "PSAdapter_23_Task_XMLResult")  
  
10. BizTalk Server から参照することになるので、このファイルの場所を忘れないようにします。  
  
## <a name="see-also"></a>参照  
 [付録 b: PeopleSoft アプリケーションの使用](../core/appendix-b-using-the-peoplesoft-application.md)