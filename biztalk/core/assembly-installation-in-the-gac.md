---
title: "GAC にアセンブリのインストール |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3b12d00c-8750-4c6d-8244-e613f955a478
caps.latest.revision: "17"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e48ec0dddcf17be70b915d2beb058f1ab2f6f576
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="assembly-installation-in-the-gac"></a>GAC でのアセンブリのインストール
各コンピューターには、コンピューター上のアプリケーション間で共有されるアセンブリを格納するグローバル アセンブリ キャッシュ (GAC) があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が実行時にメッセージを処理するためには、BizTalk アプリケーションに含まれるアセンブリが、アプリケーションを実行するコンピューターの GAC に存在する必要があります。  
  
 1 台のサーバーがアプリケーションをホストしている場合は、そのサーバーの GAC にだけアセンブリが存在する必要があります。 ただし、アプリケーションが複数のサーバーにホストされている場合は、アセンブリ内のアイテムにアクセスする必要がある各コンピューターの GAC にアプリケーションのアセンブリが存在する必要があります。 たとえば、Assembly_A を Server_1 を展開し、Assembly_A を Server_2 のホストに参加していて、Assembly_A を Server_2 の GAC にインストールする必要があります。 そうでない Server_2 は、実行時に Assembly_A にアクセスすることはできません。  
  
 特に、オーケストレーションを含むアセンブリとこれらのアセンブリが依存するアセンブリは、オーケストレーションがバインドされるホストのインスタンスを実行するサーバーの GAC に必ずインストールする必要があります。 また、ポートで使用されるマップおよびパイプラインを含むアセンブリは、ポートのアダプター ハンドラーとして機能するホストのインスタンスを実行するサーバーにインストールする必要があります。  
  
 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] からアセンブリを展開する場合は、各アセンブリの展開オプションを指定して GAC にインストールすることができます。 または、アセンブリを GAC に手動でインストールすることもできます。 さらに、アセンブリを BizTalk アプリケーションに展開した後で、展開オプションを指定してアセンブリを GAC にインストールすることもできます。  
  
 以下は、アセンブリを GAC にインストールする際に使用できるツールおよび方法をまとめたものです。  
  
-   **Microsoft Visual Studio です。** 既に触れましたが、アセンブリを GAC に自動的にインストールする、それらを展開するときに」の説明に従って、プロジェクトのプロパティを設定することができます[Visual Studio の配置プロパティを設定する方法](../core/how-to-set-deployment-properties-in-visual-studio.md)です。 付属する Gacutil コマンドライン ツールを使用してアセンブリを GAC にも手動でインストールすることができます[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]」の説明に従って、[アセンブリを GAC にインストールする方法](../core/how-to-install-an-assembly-in-the-gac.md)です。  
  
-   **BTSTask コマンド ライン ツールです。** BTSTask を使用してアセンブリを BizTalk アプリケーションに追加する場合は、アセンブリを含むアプリケーションをインポートまたはインストールする際に、オプションを指定してアセンブリを GAC にインストールすることができます。 詳細については、次を参照してください。 [AddResource コマンド: BizTalk アセンブリ](../core/addresource-command-biztalk-assembly.md)です。 参照してください[AddResource コマンド: .NET アセンブリ](../core/addresource-command-net-assembly.md)です。  
  
-   **BizTalk Server 管理コンソールです。** 管理コンソールを使用してアセンブリをアプリケーションに追加する場合は、BTSTask を使用する場合と同様に、アセンブリを含むアプリケーションをインポートまたはインストールする際に、オプションを指定してアセンブリを GAC にインストールすることができます。 詳細については、次を参照してください。 [BizTalk アセンブリをアプリケーションに追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)です。 参照してください[.NET アセンブリをアプリケーションに追加する方法](../core/how-to-add-a-net-assembly-to-an-application.md)です。  
  
     さらに、オプションを構成できますデプロイ アセンブリに配置またはアプリケーションに追加された後、いつでも」の説明に従って[BizTalk アセンブリの展開オプションを変更する方法](../core/how-to-modify-the-deployment-options-of-a-biztalk-assembly.md)です。 アセンブリを展開するときに[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]から[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]最初に、管理コンソールの展開オプションは次のように設定します。 インストール時に GAC が有効になっており、インポート時に GAC が無効になっています。 これらの設定を変更する場合、変更内容がまだされる効果場合からアセンブリを再展開[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]です。  
  
-   **ドラッグ アンド ドロップします。** Windows エクスプ ローラーを使用して、ドラッグ アンド ドロップできますアセンブリ ファイルを\< *Windows フォルダー*> \assembly です。  
  
-   **その他の方法です。** アセンブリを GAC にインストールするためのツールおよび方法は他にもあります。たとえば、Windows インストーラーやサード パーティ ベンダー製のツールを使用する方法です。  
  
> [!IMPORTANT]
>  アプリケーションを適切に動作させるために、BizTalk 管理データベースと GAC に同じバージョンのアセンブリが格納されていることを確認してください。 アセンブリを展開するときに必ずしもそのアセンブリを GAC にインストールしていない場合は、GAC と BizTalk 管理データベースに異なるバージョンのアセンブリが格納されている可能性があります。  
  
> [!IMPORTANT]
>  バージョン番号については、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] から利用できる .NET Framework ヘルプの「アセンブリのバージョン管理」を参照してください。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、.NET ポリシー ファイルの使用がサポートされません。  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリを展開します。](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)   
 [BizTalk アプリケーションの展開と管理を理解します。](../core/understanding-biztalk-application-deployment-and-management.md)