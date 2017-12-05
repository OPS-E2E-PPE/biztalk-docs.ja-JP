---
title: "ライブ データ ブックを再生成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4bd3a3fa-a550-4363-bbc0-2153226509ad
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e3e98ac5f02363c02ff422f44397fbf1f0e3b4c0
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
---
# <a name="how-to-regenerate-the-live-data-workbook"></a>ライブ データ ブックを再生成する方法
BAM ライブ データ ブックが失われるか破損した場合、BAM 管理ユーティリティを使用してブックを再生成できます。 このプロセスからにアップグレードする際にも役立ちます[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]ライブ データ ブック以降の BizTalk Server に[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]BizTalk Server と互換性がありません。  
  
 一般的な手順は次のとおりです。  
  
-   BAM 管理ユーティリティを使用して BAM データベースから BAM 定義を取得します。  
  
-   PivotTable レポートを再作成します。 get-defxml コマンドを使用して取得した XML にはアクティビティとビューしか含まれていないため、Excel 用の BAM アドインを使用して PivotTable レポートを再作成する必要があります。  
  
-   PivotTable レポートの名前を変更します。 この手順はからアップグレードする場合は、必要[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]BizTalk Server にします。 これは、必要な[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]、BAM によって BAM ブックの名前の 2 つのセット。 表示名と内部名です。 BAM 定義を取得すると、XML にはブックの内部名が含まれます。 PivotTable レポートの名前を変更して、ライブ データ ブックがデータベースに適切に接続できるようにする必要があります。  
  
-   BAM 管理ユーティリティを使用してライブ データ ブックを再生成します。  
  
### <a name="to-retrieve-the-bam-definition"></a>BAM 定義を取得するには  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  コマンド プロンプトで、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking ディレクトリに移動します。  
  
3.  型: **bm.exe get defxml-FileName:abc.xml**  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
### <a name="to-re-create-the-pivottable-reports"></a>PivotTable レポートを再作成するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**Microsoft Office**、順にクリック**Microsoft Office Excel**です。  
  
2.  クリックして、**アドイン**、タブをクリックし**XML のインポート**から、 **BAM**のドロップ ダウン リスト、**メニュー コマンド**グループ。  
  
    > [!NOTE]
    >  場合、**アドイン** タブが存在しない、指示に従って[手順 1: Microsoft Office Excel に BAM アドインを追加](http://msdn.microsoft.com/library/3400969f-0c54-4a75-979d-ad2f7af86448)BAM アドインを追加します。  
  
3.  [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking フォルダーに移動し、abc.xml ファイルを選択します。  
  
4.  使用している定義に基づいて PivotTable レポートを再作成します。  
  
5.  ブックを保存します。 これを行うには、をクリックして、**ファイル** メニューをクリックして**名前を付けて保存**とファイル名の入力を求め mynewbook.xls を入力します。  
  
### <a name="to-rename-the-pivottable-reports-optional"></a>PivotTable レポートの名前を変更するには (省略可)  
  
1.  クリックしてメモ帳を使用して BAM 定義を取得するときに作成した abc.xml ファイルを開く**開始**をクリックすると、**実行**、メモ帳」と入力[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking\abc.xml をクリックし、 **[Ok]**です。  
  
2.  検索、\<キャプション\>下にあるタグ\<BAMDefinition\>\\< 拡張子\>\\< OWC\>\\< PivotTableView\> \\< ピボット テーブル\>\\< PivotView\>\\< ラベル\>です。 このタグの内容は、いずれかの PivotTable レポートの内部名です。 次を配置することにより、他のピボット テーブル レポートの内部名を見つけることができます\<キャプション\>タグ。 開いている**mynewbook.xls**し、ピボット テーブル レポートの名前を変更する配置名を使用します。  
  
3.  更新したブックを保存します。  
  
    > [!NOTE]
    >  アップグレードする場合にのみ、この手順を実行する必要があります[!INCLUDE[btsBizTalkServer2004](../includes/btsbiztalkserver2004-md.md)]BizTalk Server にします。  
  
### <a name="to-regenerate-the-bam-live-data-workbook"></a>BAM ライブ データ ブックを再生成するには  
  
1.  をクリックして**開始**、 をクリックして**実行**、型**cmd**、順にクリック**ok**です。  
  
2.  コマンド プロンプトで、[!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]Tracking ディレクトリに移動します。  
  
3.  型: **bm.exe regenerate livedataworkbook-WorkbookName:mynewbook.xls**  
  
    > [!NOTE]
    >  ユーザー アカウント制御 (UAC) をサポートするシステムでは、管理者特権を使用してこのツールを実行することが必要な場合があります。  
  
## <a name="see-also"></a>参照  
 [BAM の管理](../core/managing-bam.md)   
 [BAM 管理ユーティリティ](../core/bam-management-utility.md)   
 [Excel 用 BAM アドインを使用するための要件](../core/requirements-for-using-the-bam-add-in-for-excel.md)   
 [手順 1: が Microsoft Office Excel に BAM アドインを追加します。](http://msdn.microsoft.com/library/3400969f-0c54-4a75-979d-ad2f7af86448)