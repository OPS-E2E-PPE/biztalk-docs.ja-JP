---
title: 補正 (BizTalk Server サンプル) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- compensations, examples
- examples, compensations
- compensations, orchestrations
ms.assetid: 9d10c7be-6a4c-44cc-bf29-78ecdf147bd1
caps.latest.revision: 32
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 56675a59714a6fabc1d54fdb594466c7568cfeba
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973451"
---
# <a name="compensation-biztalk-server-sample"></a>補正 (BizTalk Server サンプル)
補正のサンプルを使用する方法を示します、**補正**のオーケストレーションの図形。  
  
## <a name="what-this-sample-does"></a>このサンプルの処理  
 このサンプルでは、オーケストレーション内で既にコミットされたトランザクションを補正するため、次の一連の手順を実行します。  
  
1.  InfoPath フォームに顧客データを入力し、Web サービスとして公開されているオーケストレーションにデータを送信します。  
  
2.  オーケストレーションには 2 つの並列アクションがあり、 1 つ目の並列アクションでは InfoPath フォームに受信確認を返し、2 つ目の並列アクションでは Northwind および BTSCompensationSampleMailingList データベースを更新します。  
  
3.  2 番目のアクションで、オーケストレーション、受信メッセージをカスタマー リレーションシップ マネジメント (CRM) アプリケーションのメッセージ形式にマップし、更新、**顧客**Northwind データベースのテーブル。 その後、BTSCompensationSampleMailingList データベースの Mailing List テーブルを更新します。  
  
4.  どちらかの更新が失敗した場合は、外部アセンブリを呼び出すことによって Northwind データベースへの変更を補正し、元の顧客データをデータベースに再度書き込みます。  
  
## <a name="how-this-sample-is-designed-and-why"></a>このサンプルのデザイン方法とその理由  
 A**スコープ**図形は、トランザクションの実行と補正を含む、例外処理は主に使用します。 スコープは 2 つのブロックで構成されます。 最初のブロックはコンテキスト ブロックであり、2 つ目のブロックは 1 つ以上の例外処理ブロックまたは補正ブロックです。 これは .NET プログラミング言語の try-catch ステートメントと類似しています。 UpdateContact.odx オーケストレーションには 2 つの並列アクションがあります。 Try ブロックには、右側の分岐で、**スコープ**Updated Backend Systems は、実行時間の長いトランザクションの種類と、トランザクション識別子は Upd_Backend という名前の図形。 フロー下方の catch ブロックは一般的な例外をキャッチして補正を開始します。  
  
 詳細については、**スコープ**図形は、「[スコープ](../core/scopes.md)します。 参照してください[スコープ図形を構成する方法](../core/how-to-configure-the-scope-shape.md)します。  
  
> [!NOTE]
>  トランザクションの種類をアトミックまたは長時間トランザクションに設定するには、オーケストレーション自体が長時間トランザクションであることが必要です。  
  
 Try ブロックでは、という名前の 2 つのスコープが**Update CRM**と**Update Mailing**します。 これらのスコープはどちらもアトミック トランザクションです。 Update CRM スコープには try ブロックと補正ブロックがあります。 try ブロックでは外部アセンブリへのメソッド呼び出しによって Northwind データベースを更新し、 補正ブロックでは補正アクションを実行します。 Update Backend Systems スコープで例外が発生した場合は、Undo CRM 式図形内のコードによってレコードを元の状態に更新します。 これは、トリガー、**補正**例外のキャッチ ブロック内の図形。  
  
> [!NOTE]
>  アトミック トランザクションでは、トランザクション更新中にエラーが発生すると部分的な更新は自動的にロールバックされ、トランザクションの影響が除去されます。ただし、トランザクションで行われた .NET 呼び出しの影響は除去されません。  
  
> [!NOTE]
>  長時間トランザクションは、その最後のステートメントが完了したときにコミットされたと見なされます。 トランザクションが中断された場合、状態の自動的なロールバックは行われません。 これは、このサンプルで示される例外処理および補正処理を使ったプログラムによって実現できます。  
  
 Catch ブロックで 1 つである**遅延**図形が 10 秒に設定します。 補正アクションを遅らせる機能があります。 **補正**Upd_Backend トランザクションで補正アクションを開始図形。  
  
 オーケストレーションでは、入力メッセージを受信すると次の処理を実行します。  
  
1.  UpdateCrm アセンブリによって Northwind データベースの行を更新します。  
  
2.  UpdateMailingList アセンブリによって BTSCompensationSampleMailingList データベース内の一致するレコードを更新します。  
  
3.  Northwind データベースの更新で失敗した場合は例外を返し、処理を終了します。  
  
4.  BTSCompensationSampleMailingList データベースの更新で失敗した場合は例外を返し、10 秒経過後、元の顧客データを Northwind データベースに再度書き込みます。  
  
## <a name="where-to-find-this-sample"></a>このサンプルの場所  
 \<*パスのサンプル*\>\Orchestrations\Compensation\  
  
 次の表は、このサンプルのファイルとその目的を示しています。  
  
|ファイル|説明|  
|---------------|-----------------|  
|Cleanup.bat|サンプルのアンインストールに使用するバッチ ファイルです。|  
|CompensationOrchestration.btproj|オーケストレーション プロジェクトです。|  
|CompensationSample.sln|サンプル ソリューションです。|  
|CompensationSampleBinding.xml|オーケストレーションのバインド データです。インストール中に使用されます。|  
|ContactInfo.xsd|担当者情報のメッセージ スキーマです。|  
|ContactInfo.xsx|オーケストレーション デザイナーのレイアウト ファイルです。|  
|CreateSQLDataStore.sql|サンプル データベースを作成してデータを取り込む SQL スクリプトです。|  
|CrmSchema.xsd|CRM の更新メッセージ スキーマです。|  
|MailingListSchema.xsd|メーリング リストのメッセージの更新スキーマです。|  
|RemoveVirDir.vbs|Web サービスの仮想ディレクトリと物理ディレクトリを削除する、Microsoft Visual Basic Scripting Edition (VBScript) のスクリプトです。アンインストール中に使用されます。|  
|Request2Crm.btm|要求 (担当者情報) を CRM の更新メッセージに変換するメッセージ マップです。|  
|Request2MailingList.btm|要求 (担当者情報) をメーリング リストのメッセージに変換するメッセージ マップです。|  
|Setup.bat|このサンプルをインストールするバッチ ファイルです。|  
|UpdateContact.odx|オーケストレーション ファイルです。|  
|UpdateRequest2UpdateResponse.btm|要求 (担当者情報) を応答メッセージに変換するメッセージ マップです。|  
|UpdateResponse.xsd|応答メッセージ スキーマです。|  
|InfoPath\Contact Info Update.xsn|Microsoft InfoPath ファイルが Web サービスのオーケストレーションにフォームを送信するために使用します。|  
|UpdateCrm\AssemblyInfo.cs|UpdateCrm アセンブリ用のアセンブリ情報ソース ファイルです。 UpdateCrm アセンブリでは、Northwind データベースを更新します。|  
|UpdateCrm\UpdateCrm.cs|UpdateCrm アセンブリのメインのソース コードです。|  
|UpdateCrm\UpdateCRM.csproj|UpdateCrm プロジェクト ファイルです。|  
|UpdateMailingList\AssemblyInfo.cs|UpdateMailingList アセンブリ用のアセンブリ情報ソース ファイルです。 UpdateMailingList アセンブリでは、サンプル データベースを更新します。|  
|UpdateMailingList\UpdateMailingList.cs|UpdateMailingList アセンブリのメインのソース コードです。|  
|UpdateMailingList\UpdateMailingList.csproj|UpdateMailingList プロジェクト ファイルです。|  
  
## <a name="building-and-initializing-this-sample"></a>このサンプルのビルドと初期化  
  
#### <a name="to-build-and-initialize-the-compensation-sample"></a>補正のサンプルをビルドおよび初期化するには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] コマンド ウィンドウで、次のフォルダーに移動します。  
  
    \<*パスのサンプル*\>\Orchestrations\Compensation\  
  
2. Setup.bat を実行します。処理内容は次のとおりです。  
  
   -   サンプル アセンブリをビルドおよび展開します。  
  
   -   BizTalk Web サービス公開ウィザードの起動時に、次の操作を手動で行います。  
  
   1.  **BizTalk Web サービス公開ウィザードへようこそ**] ページで [**次**します。  
  
   2.  **Web サービスの作成**] ページで、[ **web サービスとして公開する BizTalk オーケストレーション**、順にクリックします**次**します。  
  
   3.  **BizTalk アセンブリ**ページを参照して選択\<*サンプル パス*\>\Orchestrations\Compensation\bin\Release\CompensationOrchestration.dll と順にクリックします**次**します。  
  
   4.  **オーケストレーションおよびポート**] ページで [**次**します。  
  
   5.  **Web サービスのプロパティ**] ページの [ **web サービスのターゲット名前空間**、型 **http://Microsoft.BizTalk.Samples.Compensation/** 、順にクリックします**次**します。  
  
   6.  **Web サービス プロジェクト**] ページの [**場所**、型 **http://localhost/CompensationOrchestrationWebServiceProxy**します。  
  
   7.  選択、 **web サービスへの匿名アクセスを許可する**チェック ボックスをオンします。  
  
   8.  選択、**作成 BizTalk 受信場所を次のアプリケーションに**チェック ボックスをオンします。  
  
   9. **作成 BizTalk 受信場所を次のアプリケーションに**ドロップダウン メニューで、 **BizTalk アプリケーション 1**クリックしてドロップダウン リストから**次**。  
  
   10. **Web サービス プロジェクトの概要**] ページで [**作成**です。  
  
   11. **BizTalk Web サービス公開ウィザードを完了**] ページで [**完了**します。  
  
3. セットアップによりポートが作成およびバインドされ、サンプル用のバックエンド データベースが作成されます。さらに、C# アセンブリがグローバル アセンブリ キャッシュに追加されます。  
  
   > [!NOTE]
   >  このサンプルを実行する前に、ビルドと初期化のプロセス中に [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] でエラーが報告されていないことを確認する必要があります。  
  
## <a name="running-this-sample"></a>このサンプルの実行  
 このサンプルをビルドおよび初期化したら、サンプルの実行前に次のことを考慮してください。  
  
- このサンプルを実行している場合[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]、IIS アプリケーション プールを作成し、BizTalk アプリケーション ユーザー Windows グループのメンバーであるアカウントにその id を設定する必要があります。 また、オーケストレーションの Web サービスの仮想ディレクトリを更新し、このアプリケーション プール内で実行されるよう設定する必要があります。  
  
- BizTalk 分離ホスト ユーザー グループに ASPNET アカウントを追加します。  
  
- BizTalk Application Users グループの db_owner アクセス許可を与える、 **BTSCompensationSampleMailingList**と**Northwind**データベース。  
  
- 場合[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が既定の場所にインストールされていない (BizTalk Server のドライブ: \Program Files\Microsoft\<バージョン\>\\) を使用する前に Contact Info Update.xsn フォームを公開する必要があります。 これを行うには次の手順を実行します。  
  
  #### <a name="to-publish-the-infopath-form"></a>InfoPath フォームを公開するには  
  
  1.  Internet Explorer で、上、**ツール** メニューのをクリックして**インターネット オプション**します。  
  
  2.  **セキュリティ**] タブで [**インターネット**、順にクリックします**レベルのカスタマイズ**します。  
  
  3.  **[その他]** セクションでは必ず、**ドメイン間でデータ ソースへのアクセス**設定が有効であり、クリックして **[ok]**。 InfoPath ユーザー インターフェイス ソリューションのスクリプト コードを実行するには、この設定が必要です。  
  
  4.  Windows エクスプ ローラーに移動します\<*サンプル パス*\>\Orchestrations\Compensation\InfoPath、右クリック**Contact Info Update.xsn**  をクリックし、  **。デザイン**します。  
  
  5.  InfoPath Contact Info Update ソリューションがデザイン モードで開きます。  
  
  6.  InfoPath Contact Info Update アプリケーションでの**ファイル** メニューのをクリックして**発行**します。  
  
  7.  公開ウィザードが表示されます。  
  
  8.  選択**このコンピューターまたはネットワーク上の共有フォルダーに**パスにソリューションを発行および\<*サンプル パス*\>\Orchestrations\Compensation\InfoPath\Contact InfoUpdate.xsn します。  
  
  9. デザイン モードの InfoPath を閉じます。  
  
- 以上で、サンプルの実行準備が整いました。  
  
  #### <a name="to-run-the-compensation-sample"></a>補正のサンプルを実行するには  
  
  1.  ダブルクリック**Contact Info Update.xsn** InfoPath で開きます。  
  
  2.  両方のデータベースに存在するアカウントのフォームに記入します。 たとえば、Northwind の Customers テーブルの既存のアカウント ID "ALFKI" を使用します。  
  
  3.  **ファイル**メニューの [**送信**、] をクリック**送信**します。  
  
  4.  応答ドキュメントに表示されます、 \<*サンプル パス*\>\Orchestrations\Compensation\Out フォルダーと、Northwind と BTSCompensationSampleMailingList データベースの両方を更新する必要がありますInfoPath フォームから新しいデータです。  
  
      > [!NOTE]
      >  BTSCompensationSampleMailingList データベースを接続解除するか、オフラインにして、オーケストレーションで実行される補正アクションをテストできます。 Northwind データベースで先にレコードが更新されることを確認します。 その後、オーケストレーションが BTSCompensationSampleMailingList データベースを更新しようとすると、データベースが接続解除されているために、更新は失敗します。 したがって、例外が発行され、10 秒が経過した後に補正アクションが実行されて、元の顧客データが Northwind データベースに再度書き込まれます。  
  
      > [!NOTE]
      >  "ユーザー 'IIS APPPOOL\DefaultAppPool' はログインできませんでした。" というエラーが発生する場合があります。 これは、トークンベースのサーバー アクセスの検証エラーが原因となっている可能性があります。 このエラーを解決するには、新しいアプリケーション プールを作成し、そのプールで管理アカウントを使用します。  
  
## <a name="uninstalling-this-sample"></a>このサンプルのアンインストール  
  
#### <a name="to-uninstall-the-compensation-sample"></a>補正のサンプルをアンインストールするには  
  
1. [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] コマンド ウィンドウで、次のフォルダーに移動します。  
  
    \<*パスのサンプル*\>\Orchestrations\Compensation\  
  
2. Cleanup.bat を実行します。  
  
## <a name="see-also"></a>参照  
 [オーケストレーション (BizTalk Server サンプル フォルダー)](../core/orchestrations-biztalk-server-samples-folder.md)