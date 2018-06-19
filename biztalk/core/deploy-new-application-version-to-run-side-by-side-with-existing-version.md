---
title: 既存のバージョンがサイド バイ サイドで実行するアプリケーションの新しいバージョンを展開する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1677c6a5-2c4c-4d70-ab83-f7e0bb3aaf6e
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 053145729546453b959dc35c7901932c1c8690c5
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241586"
---
# <a name="how-to-deploy-a-new-version-of-an-application-to-run-side-by-side-with-an-existing-version"></a>既存のバージョンと並行して実行するアプリケーションの新しいバージョンを展開する方法
新しいバージョンのサイド バイ サイドで実行するアプリケーションを展開する方法、既存のバージョン。 

## <a name="overview"></a>概要
一度にすべてのパートナーを対象にするのではなく、最初は一部のビジネス パートナーだけが最新バージョンを使用できるようにするなど、アプリケーションの大幅アップグレードを段階的に実行する場合にこの方法を使用します。 この方法を使用すると、新しいバージョンへの完全な切り替えの準備ができるまで、新しいバージョンをまだ使用していないユーザーに、既存のアプリケーションを実行してサービスを提供し続けることができます。 このシナリオの背景情報については、次を参照してください。[シナリオ: 次の 2 つのバージョンのアプリケーションを展開する](../core/scenario-deploying-two-versions-of-an-application.md)です。  
  
 アセンブリ バージョンを作成する場合と異なり、アプリケーション バージョンは、バージョン番号を増やす方法では作成しません。 代わりに、元のアプリケーションとは異なる名前を持つ新しいアプリケーションを作成し、それに新しいバージョンのアプリケーション アイテムを取り込みます。  
  
 アセンブリなどの多くの種類のアイテムは、BizTalk グループ内の 1 つのアプリケーションにしか存在できません。したがって、グループ内に既に存在するアセンブリを新しいアプリケーションへ展開するには、そのバージョン番号を増やす必要があります。 詳細については、次を参照してください。[成果物をする必要がありますする内で一意のアプリケーションまたはグループ](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)です。  

## <a name="prerequisites"></a>前提条件  
メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。 自分のアカウントも、ローカル ファイル システムおよびグローバル アセンブリ キャッシュに対する読み取り/書き込み権限が必要です。 ローカル コンピューターの管理者アカウントには、このアクセス許可があります。  

詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)です。 
  
## <a name="deploy-a-new-version-of-an-application"></a>新しいバージョンのアプリケーションを展開します。  
  
1.  Visual Studio で、アプリケーションの新しいバージョンに展開するアセンブを必要に応じて変更します。  
  
2.  次のように、各アセンブリのバージョン番号を増やします。  
  
    1.  ソリューション エクスプ ローラーで、BizTalk プロジェクトを右クリックし、をクリックして**プロパティ**をプロジェクトのプロジェクト デザイナーを起動します。  
  
    2.  をクリックして、**アプリケーション**タブがアクティブでない場合、クリックして**アセンブリ情報**ボタンをクリックします。  
  
    3.  アセンブリ バージョン番号を大きくし、 **OK**です。  
  
    4.  プロジェクトを保存します。  
  
    > [!NOTE]
    >  パイプライン デザイナー オブジェクト モデルを使用して、アセンブリ バージョンを増やす際のスキーマの競合を避けます。  
  
3.  ソリューションの各プロジェクトの展開プロパティで、次の操作を行います。  
  
    -   アプリケーション名を新しいアプリケーションに対して使用する名前に変更します。  
  
    -   グローバル アセンブリ キャッシュ (GAC) 内のアセンブリをインストールするためのオプションが選択されていることを確認します。  
  
     手順については、次を参照してください。 [Visual Studio の配置プロパティを設定する方法](../core/how-to-set-deployment-properties-in-visual-studio.md)です。 ソリューションを展開するときに、アセンブリは、新しいアプリケーションに展開され、GAC にインストールされます。  
  
4.  アセンブリを含んでいるソリューションを展開します。 手順については、次を参照してください。[を Visual Studio から BizTalk アセンブリを展開する方法](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)です。  
  
5.  新しい受信ポート、およびパートナーがメッセージを送信する際の送信先となる新しい 1 つ以上の URL を指定する任意の必要な受信場所を作成します。 手順については、次を参照してください。[受信ポートを作成する方法](../core/how-to-create-a-receive-port.md)です。 参照してください[受信場所を作成する方法](../core/how-to-create-a-receive-location.md)です。  
  
6.  説明に従って、必要に応じて、適切な送信ポートを作成[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)です。  
  
7.  バインドを新しく作成された新しいアプリケーションが受信および」の説明に従って、送信ポート、[アプリケーションを構成する方法](../core/how-to-configure-an-application.md)です。  
  
8.  」の説明に従って、テスト環境から .msi ファイルにアプリケーションをエクスポート[を BizTalk アプリケーションをエクスポートする方法](../core/how-to-export-a-biztalk-application.md)です。  
  
    > [!NOTE]
    >  次の手順に従って、アプリケーションをテストし、実稼動環境へ展開することができます。 開発、テスト、ステージング、および実稼働環境でのアプリケーション展開タスクの詳細については、次を参照してください。[アプリケーション展開作業](../core/application-deployment-tasks.md)です。  
  
9. 」の説明に従って、実稼働環境で BizTalk グループにアプリケーションの .msi ファイルをインポート[を BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)です。 アプリケーションは、参照を必要とする場合、またはに追加できます MSI のインポート ウィザードを使用しているときに後で」の説明に従って[を別のアプリケーションへの参照を追加する方法](../core/how-to-add-a-reference-to-another-application.md)です。  
  
10. 」の説明に従って、それを実行する各ホスト インスタンスで、新しいアプリケーションをインストール[を BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)です。 更新されたそれぞれのアセンブリが、アセンブリをホストする各コンピューターの GAC にインストールされたことを確認します。 必要に応じて、アセンブリを GAC にインストール、」の説明に従って[アセンブリを GAC にインストールする方法](../core/how-to-install-an-assembly-in-the-gac.md)です。  
  
11. 説明に従って、アプリケーションの完全な開始を行う[起動し、BizTalk アプリケーションを停止する方法](../core/how-to-start-and-stop-a-biztalk-application.md)です。  
  
12. パートナーに新しい URL へのメッセージの送信を開始する必要があることを通知します。 パートナーがこれを実行すると、アプリケーションによって指定したパートナーに対するメッセージの処理が開始されます。  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションの更新](../core/updating-biztalk-applications.md)