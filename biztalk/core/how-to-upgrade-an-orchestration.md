---
title: オーケストレーションをアップグレードする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ef3f032f-28a1-4d52-9d85-d5748c9e9682
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96d3b340d796d2cf3a63e206a74b0faa43acafa6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333642"
---
# <a name="how-to-upgrade-an-orchestration"></a>オーケストレーションをアップグレードする方法
オーケストレーションの実行時間の長いトランザクションを処理またはが送信請求-応答ポートからの応答を待機しているときに、運用環境で実行されているオーケストレーションを更新する方法。

## <a name="overview"></a>概要
 オーケストレーションは、実行時間の長いトランザクションを処理できない、更新する」の説明に従って[チェックリスト。BizTalk アプリケーション内のアイテムの更新](../core/checklist-update-the-artifacts-in-a-biztalk-application.md)します。 オーケストレーションでは、実行時間の長いトランザクションを処理するときにただし、切り替えることはできません、オーケストレーションの更新されたバージョンにすぐにします。 メッセージの処理を完了する元のバージョンを許可するが失われないようにする必要があります。 これを行うには、元の 1 つとして、同じアプリケーションに更新されたオーケストレーションを展開します。 元のバージョンを停止し、以前のバージョンがインフライト メッセージの処理を続行中には、すべての新しいメッセージを受信するように、更新されたバージョンを開始します。 元のオーケストレーションは、そのすべてのメッセージの処理が終了したらが展開された BizTalk アプリケーションから解除します。  
  
 このシナリオの詳細については、次を参照してください。[シナリオ。アプリケーション アイテムの更新](../core/scenario-updating-application-artifacts.md)します。  
  
> [!IMPORTANT]
>  1 つ以上のオーケストレーションがバインドされている場合、同じ受信ポート、および各オーケストレーションを開始または参加している、システムに重複するメッセージが発生します。  
  
> [!NOTE]
>  新しいオーケストレーションにアップグレードするときに一部のオーケストレーション インスタンスできますになる中断 (再開可能) 負荷が高い新旧のオーケストレーションと、アップグレード中に新しいオーケストレーション間の競合状態が原因です。 これらのオーケストレーション インスタンスを手動で再開するを参照してください。[中断したオーケストレーション インスタンスの再開方法](../core/how-to-resume-suspended-orchestration-instances.md)します。

## <a name="prerequisites"></a>前提条件  
メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。 自分のアカウントも、ローカル ファイル システムおよびグローバル アセンブリ キャッシュに対する読み取り/書き込みアクセス許可が必要です。 ローカル コンピューターの管理者アカウントには、このアクセス許可があります。  

詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)します。 
 
## <a name="update-an-orchestration"></a>オーケストレーションを更新します。  
  
1.  オーケストレーションに必要な変更を行います。  
  
2.  次のように、アセンブリのバージョン番号を増やします。  
  
    1.  ソリューション エクスプ ローラーで BizTalk プロジェクトを右クリックし をクリックし、**プロパティ**をプロジェクトのプロジェクト デザイナーを起動します。  
  
    2.  をクリックして、**アプリケーション** タブがアクティブでない場合、クリックして**アセンブリ情報**します。  
  
    3.  右側のウィンドウで、アセンブリのバージョン番号を増やします。 メジャーまたはマイナー バージョン番号のみを増やす必要があります。 メジャー バージョン番号は、シーケンスの最初の桁 (**0**.0.0.0); マイナー バージョン番号は、シーケンス内の 2 番目の数字 (0 **。0**.0.0) です。 BizTalk Server では、0.0 などのシーケンスの後のバージョン番号の変更は認識されません。**0**.0 や 0.0.0 **。0**します。  
  
    4.  をクリックして**OK**を閉じる、**アセンブリ情報** ダイアログ ボックス。  
  
    5.  プロジェクトを保存します。  
  
3.  Visual Studio から BizTalk アプリケーションにアセンブリを展開します。 手順については、次を参照してください。 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開する](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)します。 GAC にアセンブリをインストールする展開オプションを選択することを確認します。  
  
4.  オーケストレーションを含むアセンブリをテストします。  
  
5.  」の説明に従って、.msi ファイルに、テスト環境でのアプリケーションからアセンブリをエクスポート[BizTalk アプリケーションのエクスポート方法](../core/how-to-export-a-biztalk-application.md)します。  
  
    > [!NOTE]
    >  次の手順を使用するには、運用環境に展開すると、アセンブリをテストします。 開発、テスト、ステージング、および運用環境でアプリケーション展開作業の詳細については、次を参照してください。[アプリケーション展開作業](../core/application-deployment-tasks.md)します。  
  
6.  」の説明に従って、更新するオーケストレーションを含む実稼働環境で BizTalk アプリケーションに .msi ファイルをインポート[BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)します。  
  
7.  」の説明に従って、元のオーケストレーションとして同じバインディングを使用して、更新されたオーケストレーションをバインド[オーケストレーションのバインドを構成する方法](../core/how-to-configure-bindings-for-an-orchestration.md)します。  
  
8.  元のオーケストレーションの参加を解除し、更新されたオーケストレーションを開始します。 メッセージの消失を回避する必要がありますこれを行う」の説明に従って、プログラムで[展開とプログラム、オーケストレーションの新しいバージョンを開始](../core/deploying-and-starting-a-new-version-of-an-orchestration-programmatically.md)します。 」の説明に従って、手動でこれらの手順を実行する代わりに、[オーケストレーションを参加解除する方法](../core/how-to-unenlist-an-orchestration.md)、[オーケストレーションを参加させる方法](../core/how-to-enlist-an-orchestration.md)、および[オーケストレーションを開始する方法](../core/how-to-start-an-orchestration.md).  
  
9. システムの監視」の説明に従って、グループのハブを使用して元のオーケストレーションのバージョンのインスタンスがクエリのビューをページ[オーケストレーションのインスタンス情報を表示する方法](../core/how-to-view-instance-information-for-an-orchestration.md)します。  
  
10. 説明されているように、アプリケーションから元のオーケストレーションを展開解除、すべてのアクティブ、退避済み、および中断されたインスタンスが完了したら、[オーケストレーションをアプリケーションから削除する方法](../core/how-to-remove-an-orchestration-from-an-application.md)します。  
  
11. 必要に応じて」の説明に従って、アプリケーションを実行している各コンピューターの GAC から元のアセンブリ バージョンをアンインストール[GAC からアセンブリをアンインストールする方法](http://msdn.microsoft.com/library/464706a8-f902-4d05-a724-19169facd2b4)します。  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションの更新](../core/updating-biztalk-applications.md)   
 [オーケストレーションの管理](../core/managing-orchestrations.md)