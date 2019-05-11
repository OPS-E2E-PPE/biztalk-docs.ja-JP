---
title: PeopleSoft で XML またはスキーマの生成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- generating schemas
- schemas, generating
- generating XML
- XML, generating
ms.assetid: adfe2936-0dc2-42d2-b26a-718f8cc57eff
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3046a6cb3dc90db69d7d113bf08b92d8c4606bab
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387754"
---
# <a name="generating-xml-or-schema-in-peoplesoft"></a>PeopleSoft で XML またはスキーマの生成
次の手順では、PeopleSoft Enterprise を使用して XML ファイルを作成し、PeopleSoft イベントをトリガーする方法について説明します。 これを行うには、PeopleSoft 環境で何かを変更します。 変更は、監視するために、オーケストレーションで設定ファイルのフォルダーに送信される XML ファイルをアクティブにします。 後で BizTalk server の XML をインポートし、スキーマを生成します。  
  
> [!NOTE]
>  場所の値に加えられた変更が XML ドキュメントを生成する場所を MSEXTERNAL ノードに関連付けると、イベントをトリガーします。 参加と、オーケストレーションの開始、場所の画面に、PeopleSoft の画面間を移動できます。 場所の値に変更を加える変更を保存して、対応する XML が \out ディレクトリに表示されます。  
  
### <a name="to-generate-xml-or-schema-in-peoplesoft"></a>PeopleSoft で XML またはスキーマを生成するには  
  
1. PeopleSoft アプリケーションでポイントして**Set up Financials**、 をポイント**Supply Chain**、 をポイント**共通定義**、 をポイント**場所**、し、**場所**します。  
  
2. **場所**画面で、次の情報を入力します。  
  
   - **ID を設定します。** 入力**共有**します。  
  
   - **Location Code:** 始まるコードを入力`WKLOC`します。  
  
     ![](../core/media/psadapter-18-task-sharesearch.gif "PSAdapter_18_Task_ShareSearch")  
  
3. クリックして**検索**、順にクリックします**Correct History**して画面を**編集**モード。  
  
    ![](../core/media/psadapter-19-task-correcthistory.gif "PSAdapter_19_Task_CorrectHistory")  
  
4. クリックして、画面上のフィールドに変更を加える**保存**します。  
  
5. をポイント**PeopleTools**、 をポイント**Integration Broker**、 をポイント**モニター**、し、**メッセージの監視**します。  
  
    ![](../core/media/psadapter-20-task-monitormessage.gif "PSAdapter_20_Task_MonitorMessage")  
  
6. 確認します**チャネルの種類**は**メッセージ インスタンス**、 をクリックし、**更新**します。  
  
7. **完了**列番号をクリックします。  
  
8. リストの一番下までスクロールし、**詳細**リンクを**LOCATION_SYNC**メッセージ。  
  
    ![](../core/media/psadapter-21-task-detailslink.gif "PSAdapter_21_Task_DetailsLink")  
  
9. をクリックして**XML を表示**上、 **MSEXTERNAL**ノード。  
  
     ![](../core/media/psadapter-22-task-viewxml.gif "PSAdapter_22_Task_ViewXML")  
  
     コピーして、BizTalk Server プロジェクトでアクセスできるファイルに XML の内容を貼り付けます。  
  
     ![](../core/media/psadapter-23-task-xmlresult.gif "PSAdapter_23_Task_XMLResult")  
  
10. は、ファイルの場所を忘れないでください BizTalk Server で参照します。  
  
## <a name="see-also"></a>参照  
 [付録 b:PeopleSoft アプリケーションの使用](../core/appendix-b-using-the-peoplesoft-application.md)