---
title: "オーケストレーションをアップグレードする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ef3f032f-28a1-4d52-9d85-d5748c9e9682
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: edd9fa8e98b62ec92b1313cc1028efc5320ce17e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-upgrade-an-orchestration"></a>オーケストレーションをアップグレードする方法
オーケストレーションの実行時間の長いトランザクションを処理またはが、送信請求-応答ポートからの応答を待機しているときに、実稼働環境で実行されているオーケストレーションを更新する方法です。

## <a name="overview"></a>概要
 オーケストレーションは、実行時間の長いトランザクションを処理できない、更新する」の説明に従って[チェックリスト: BizTalk アプリケーション内のアイテムの更新](../core/checklist-update-the-artifacts-in-a-biztalk-application.md)です。 しかし、オーケストレーションで長時間トランザクションが処理される場合は、オーケストレーションの更新されたバージョンにすぐに切り替えることはできません。 メッセージが失われないように、元のバージョンでメッセージの処理を完了させる必要があります。 これを行うには、元のオーケストレーションと同じアプリケーションに、更新されたオーケストレーションを展開します 次に、元のバージョンを停止し、更新されたバージョンを開始して、前のバージョンがインフライト メッセージを引き続き処理する一方で、更新されたバージョンが新しいメッセージをすべて受信するようにします。 元のオーケストレーションですべてのメッセージ処理が完了したら、展開されている BizTalk アプリケーションから元のオーケストレーションを展開解除します。  
  
 このシナリオの詳細については、次を参照してください。[シナリオ: アプリケーション アイテムの更新](../core/scenario-updating-application-artifacts.md)です。  
  
> [!IMPORTANT]
>  複数のオーケストレーションが同じ受信ポートにバインドされており、各オーケストレーションが開始または参加している場合は、重複メッセージが発生します。  
  
> [!NOTE]
>  新しいオーケストレーションにアップグレードする際に、アップグレード中に新旧のオーケストレーション間で競合状態が発生したことにより、一部のオーケストレーション インスタンスが高負荷で中断 (再開可能) されることがあります。 これらのオーケストレーション インスタンスを手動で再開するを参照してください。[中断したオーケストレーション インスタンスの再開方法](../core/how-to-resume-suspended-orchestration-instances.md)です。

## <a name="prerequisites"></a>前提条件  
メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。 自分のアカウントも、ローカル ファイル システムおよびグローバル アセンブリ キャッシュに対する読み取り/書き込み権限が必要です。 ローカル コンピューターの管理者アカウントには、このアクセス許可があります。  

詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)です。 
 
## <a name="update-an-orchestration"></a>オーケストレーションを更新します。  
  
1.  オーケストレーションに必要な変更を加えます。  
  
2.  次のように、アセンブリのバージョン番号を増分します。  
  
    1.  ソリューション エクスプ ローラーで、BizTalk プロジェクトを右クリックし、をクリックして**プロパティ**プロジェクトのプロジェクト デザイナーを起動します。  
  
    2.  クリックして、**アプリケーション**タブがアクティブでない場合、クリックして**アセンブリ情報**です。  
  
    3.  右ペインで、アセンブリ バージョン番号を増分します。 メジャー バージョン番号またはマイナー バージョン番号だけを増分してください。 メジャー バージョン番号は、シーケンスの最初の桁 (**0**.0.0.0); マイナー バージョン番号は、シーケンス内の 2 番目の数字 (0 **。0**.0.0) です。 BizTalk Server では、0.0 などのシーケンスの後のバージョン番号の変更は認識されません。**0**.0 や 0.0.0 と表示されます**。0**します。  
  
    4.  をクリックして**OK**を閉じる、**アセンブリ情報** ダイアログ ボックス。  
  
    5.  プロジェクトを保存します。  
  
3.  Visual Studio から BizTalk アプリケーションにアセンブリを展開します。 手順については、次を参照してください。 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)です。 GAC でアセンブリをインストールする展開オプションを選択してください。  
  
4.  オーケストレーションを含むアセンブリをテストします。  
  
5.  」の説明に従って、.msi ファイルに、テスト環境でのアプリケーションからアセンブリをエクスポート[を BizTalk アプリケーションをエクスポートする方法](../core/how-to-export-a-biztalk-application.md)です。  
  
    > [!NOTE]
    >  次の手順に従って、アセンブリをテストし、実稼動環境へ展開することができます。 開発、テスト、ステージング、および実稼働環境でのアプリケーション展開タスクの詳細については、次を参照してください。[アプリケーション展開作業](../core/application-deployment-tasks.md)です。  
  
6.  .Msi ファイルを更新する、」の説明に従って、オーケストレーションを含む、運用環境で BizTalk アプリケーションをインポート[を BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)です。  
  
7.  」の説明に従って、元のオーケストレーションとして同じバインディングを使用して、更新されたオーケストレーションをバインド[オーケストレーションのバインドを構成する方法](../core/how-to-configure-bindings-for-an-orchestration.md)です。  
  
8.  元のオーケストレーションを参加解除して、更新されたオーケストレーションを開始します。 メッセージの消失を回避するのにはこれを行う」の説明に従って、プログラムによって[展開とプログラム、オーケストレーションの新しいバージョンを開始](../core/deploying-and-starting-a-new-version-of-an-orchestration-programmatically.md)です。 」の説明に従って、手動でこれらの手順を実行する代わりに、[オーケストレーションを参加解除する方法](../core/how-to-unenlist-an-orchestration.md)、[にオーケストレーションを参加させる方法](../core/how-to-enlist-an-orchestration.md)、および[オーケストレーションを開始する方法](../core/how-to-start-an-orchestration.md).  
  
9. システムの監視」の説明に従って、グループ ハブを使用して元のオーケストレーションのバージョンのインスタンスがクエリのビューをページ[オーケストレーションのインスタンス情報を表示する方法](../core/how-to-view-instance-information-for-an-orchestration.md)です。  
  
10. 説明したように、アプリケーションから元のオーケストレーションを展開解除、すべてのアクティブ、退避済み、および中断されたインスタンスが完了したら、[アプリケーションからオーケストレーションを削除する方法](../core/how-to-remove-an-orchestration-from-an-application.md)です。  
  
11. 必要に応じて、」の説明に従って、アプリケーションを実行する各コンピューターの GAC から元のアセンブリ バージョンをアンインストール[GAC からアセンブリをアンインストールする方法](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4)です。  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションの更新](../core/updating-biztalk-applications.md)   
 [オーケストレーションの管理](../core/managing-orchestrations.md)