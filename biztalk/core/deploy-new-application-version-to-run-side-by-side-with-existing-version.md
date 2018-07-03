---
title: 既存のバージョンとサイド バイ サイドでを実行するアプリケーションの新しいバージョンをデプロイする方法 |Microsoft Docs
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
ms.openlocfilehash: 9399543219613809efb5f8a40c9d2129ba4976ad
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988859"
---
# <a name="how-to-deploy-a-new-version-of-an-application-to-run-side-by-side-with-an-existing-version"></a>既存のバージョンと並行して実行するアプリケーションの新しいバージョンを展開する方法
新しいバージョンのサイド バイ サイドで実行されるアプリケーションをデプロイする方法、既存のバージョン。 

## <a name="overview"></a>概要
一度にすべてのパートナーを対象にするのではなく、最初は一部のビジネス パートナーだけが最新バージョンを使用できるようにするなど、アプリケーションの大幅アップグレードを段階的に実行する場合にこの方法を使用します。 この方法を使用すると、新しいバージョンへの完全な切り替えの準備ができるまで、新しいバージョンをまだ使用していないユーザーに、既存のアプリケーションを実行してサービスを提供し続けることができます。 このシナリオの背景については、次を参照してください。[シナリオ: 2 つのバージョンのアプリケーションを展開する](../core/scenario-deploying-two-versions-of-an-application.md)します。  
  
 アセンブリ バージョンを作成する場合と異なり、アプリケーション バージョンは、バージョン番号を増やす方法では作成しません。 代わりに、元のアプリケーションとは異なる名前を持つ新しいアプリケーションを作成し、それに新しいバージョンのアプリケーション アイテムを取り込みます。  
  
 アセンブリなどの多くの種類のアイテムは、BizTalk グループ内の 1 つのアプリケーションにしか存在できません。したがって、グループ内に既に存在するアセンブリを新しいアプリケーションへ展開するには、そのバージョン番号を増やす必要があります。 詳細については、次を参照してください。[成果物をする必要がありますする内で一意で、アプリケーションまたはグループ](../core/artifacts-that-must-be-unique-in-an-application-or-group.md)します。  

## <a name="prerequisites"></a>前提条件  
メンバーであるアカウントでサインイン、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理者グループ。 自分のアカウントも、ローカル ファイル システムおよびグローバル アセンブリ キャッシュに対する読み取り/書き込みアクセス許可が必要です。 ローカル コンピューターの管理者アカウントには、このアクセス許可があります。  

詳細なアクセス許可についてを参照してください。[を展開すると、BizTalk アプリケーションの管理に必要なアクセス許可](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)、および[最低限のセキュリティ権限](https://social.technet.microsoft.com/wiki/contents/articles/24590.minimum-security-rights-for-biztalk-server-2006-to-2016.aspx)します。 
  
## <a name="deploy-a-new-version-of-an-application"></a>新しいバージョンのアプリケーションを展開します。  
  
1. Visual Studio で、アプリケーションの新しいバージョンに展開するアセンブを必要に応じて変更します。  
  
2. 次のように、各アセンブリのバージョン番号を増やします。  
  
   1.  ソリューション エクスプ ローラーで BizTalk プロジェクトを右クリックし をクリックし、**プロパティ**をプロジェクトのプロジェクト デザイナーを起動します。  
  
   2.  をクリックして、**アプリケーション** タブがアクティブでない場合、クリックして**アセンブリ情報**ボタンをクリックします。  
  
   3.  アセンブリのバージョン番号を増やし をクリックし、 **OK**します。  
  
   4.  プロジェクトを保存します。  
  
   > [!NOTE]
   >  パイプライン デザイナー オブジェクト モデルを使用して、アセンブリ バージョンを増やす際のスキーマの競合を避けます。  
  
3. ソリューションの各プロジェクトの展開プロパティで、次の操作を行います。  
  
   - アプリケーション名を新しいアプリケーションに対して使用する名前に変更します。  
  
   - グローバル アセンブリ キャッシュ (GAC) 内のアセンブリをインストールするためのオプションが選択されていることを確認します。  
  
     手順については、次を参照してください。 [Visual Studio の配置プロパティを設定する方法](../core/how-to-set-deployment-properties-in-visual-studio.md)します。 ソリューションを展開するときに、アセンブリは、新しいアプリケーションに展開され、GAC にインストールされます。  
  
4. アセンブリを含んでいるソリューションを展開します。 手順については、次を参照してください。 [Visual Studio から BizTalk アセンブリを展開する方法](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)します。  
  
5. 新しい受信ポート、およびパートナーがメッセージを送信する際の送信先となる新しい 1 つ以上の URL を指定する任意の必要な受信場所を作成します。 手順については、次を参照してください。[受信ポートを作成する方法](../core/how-to-create-a-receive-port.md)します。 参照してください[受信場所を作成する方法](../core/how-to-create-a-receive-location.md)します。  
  
6. 」の説明に従って、必要に応じて、適切な送信ポートを作成[送信ポートを作成する方法](../core/how-to-create-a-send-port2.md)します。  
  
7. バインドを新しく作成された新しいアプリケーションが受信および」の説明に従って、送信ポート、[アプリケーションを構成する方法](../core/how-to-configure-an-application.md)します。  
  
8. 」の説明に従って、テスト環境から .msi ファイルにアプリケーションをエクスポート[BizTalk アプリケーションのエクスポート方法](../core/how-to-export-a-biztalk-application.md)します。  
  
   > [!NOTE]
   >  次の手順に従って、アプリケーションをテストし、実稼動環境へ展開することができます。 開発、テスト、ステージング、および運用環境でアプリケーション展開作業の詳細については、次を参照してください。[アプリケーション展開作業](../core/application-deployment-tasks.md)します。  
  
9. 」の説明に従って、運用環境での BizTalk グループにアプリケーションの .msi ファイルをインポート[BizTalk アプリケーションをインポートする方法](../core/how-to-import-a-biztalk-application.md)します。 アプリケーションでは、参照が必要とする場合または追加できますに MSI のインポート ウィザードを使用しているときに後で説明するよう[別のアプリケーションへの参照を追加する方法](../core/how-to-add-a-reference-to-another-application.md)します。  
  
10. 」の説明に従って、新しいアプリケーションを実行する各ホスト インスタンスでインストール[BizTalk アプリケーションをインストールする方法](../core/how-to-install-a-biztalk-application.md)します。 更新されたそれぞれのアセンブリが、アセンブリをホストする各コンピューターの GAC にインストールされたことを確認します。 必要に応じて、アセンブリを GAC にインストール、」の説明に従って[を GAC にアセンブリをインストールする方法](../core/how-to-install-an-assembly-in-the-gac.md)します。  
  
11. 説明に従って、アプリケーションの完全な開始実行[BizTalk アプリケーション開始および停止する方法](../core/how-to-start-and-stop-a-biztalk-application.md)します。  
  
12. パートナーに新しい URL へのメッセージの送信を開始する必要があることを通知します。 パートナーがこれを実行すると、アプリケーションによって指定したパートナーに対するメッセージの処理が開始されます。  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションの更新](../core/updating-biztalk-applications.md)