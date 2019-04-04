---
title: GAC でアセンブリのインストール |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3b12d00c-8750-4c6d-8244-e613f955a478
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ddcafc37ade0dc4ea57b0271224e09ebe61e0a5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37012595"
---
# <a name="assembly-installation-in-the-gac"></a>GAC でのアセンブリのインストール
各コンピューターには、コンピューター上のアプリケーション間で共有されるアセンブリを格納するグローバル アセンブリ キャッシュ (GAC) があります。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] が実行時にメッセージを処理するためには、BizTalk アプリケーションに含まれるアセンブリが、アプリケーションを実行するコンピューターの GAC に存在する必要があります。  
  
 1 台のサーバーがアプリケーションをホストしている場合は、そのサーバーの GAC にだけアセンブリが存在する必要があります。 ただし、アプリケーションが複数のサーバーにホストされている場合は、アセンブリ内のアイテムにアクセスする必要がある各コンピューターの GAC にアプリケーションのアセンブリが存在する必要があります。 たとえば、Assembly_A を Server_1 を展開し、Assembly_A を Server_2 のホストに参加していて、Assembly_A を Server_2 の GAC にインストールする必要があります。 そうでない場合、Server_2 はランタイム処理中に Assembly_A にアクセスできません。  
  
 特に、オーケストレーションを含むアセンブリとこれらのアセンブリが依存するアセンブリは、オーケストレーションがバインドされるホストのインスタンスを実行するサーバーの GAC に必ずインストールする必要があります。 また、ポートで使用されるマップおよびパイプラインを含むアセンブリは、ポートのアダプター ハンドラーとして機能するホストのインスタンスを実行するサーバーにインストールする必要があります。  
  
 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] からアセンブリを展開する場合は、各アセンブリの展開オプションを指定して GAC にインストールすることができます。 または、アセンブリを GAC に手動でインストールすることもできます。 さらに、アセンブリを BizTalk アプリケーションに展開した後で、展開オプションを指定してアセンブリを GAC にインストールすることもできます。  
  
 以下は、アセンブリを GAC にインストールする際に使用できるツールおよび方法をまとめたものです。  
  
- **Microsoft Visual Studio。** 既に説明したように、アセンブリを GAC に自動的にインストールするには、展開するとき」の説明に従って、プロジェクトのプロパティを設定する[Visual Studio の配置プロパティを設定する方法](../core/how-to-set-deployment-properties-in-visual-studio.md)します。 付属する Gacutil コマンドライン ツールを使用してアセンブリを GAC にも手動でインストールすることができます[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]」の説明に従って、[を GAC にアセンブリをインストールする方法](../core/how-to-install-an-assembly-in-the-gac.md)します。  
  
- **BTSTask コマンド ライン ツールです。** BTSTask を使用してアセンブリを BizTalk アプリケーションに追加する場合は、アセンブリを含むアプリケーションをインポートまたはインストールする際に、オプションを指定してアセンブリを GAC にインストールすることができます。 詳細については、[AddResource コマンド: BizTalk アセンブリ](../core/addresource-command-biztalk-assembly.md)を参照してください。 参照してください[AddResource コマンド: .NET アセンブリ](../core/addresource-command-net-assembly.md)します。  
  
- **BizTalk Server 管理コンソール。** 管理コンソールを使用してアセンブリをアプリケーションに追加する場合は、BTSTask を使用する場合と同様に、アセンブリを含むアプリケーションをインポートまたはインストールする際に、オプションを指定してアセンブリを GAC にインストールすることができます。 詳細については、[アプリケーションに BizTalk アセンブリを追加する方法](../core/how-to-add-a-biztalk-assembly-to-an-application.md)を参照してください。 参照してください[.NET アセンブリをアプリケーションに追加する方法](../core/how-to-add-a-net-assembly-to-an-application.md)します。  
  
   さらに、オプションを構成できますデプロイ アセンブリに展開または、アプリケーションに追加した後、いつでも」の説明に従って[BizTalk アセンブリの展開オプションを変更する方法](../core/how-to-modify-the-deployment-options-of-a-biztalk-assembly.md)します。 アセンブリを展開するときに[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]から[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]最初の管理コンソールの展開オプションは次のように設定: インストール時に GAC が有効になっているし、インポート時に GAC が無効になっています。 これらの設定に変更を加えると、変更内容は引き続き有効になってからアセンブリを再展開する場合[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]します。  
  
- **ドラッグ アンド ドロップします。** Windows エクスプ ローラーを使用できるドラッグ アンド ドロップするアセンブリ ファイルを\< *Windows フォルダー*\>\assembly します。  
  
- **その他の方法です。** アセンブリを GAC にインストールするためのツールおよび方法は他にもあります。たとえば、Windows インストーラーやサード パーティ ベンダー製のツールを使用する方法です。  
  
> [!IMPORTANT]
>  アプリケーションを適切に動作させるために、BizTalk 管理データベースと GAC に同じバージョンのアセンブリが格納されていることを確認してください。 アセンブリを展開するときに必ずしもそのアセンブリを GAC にインストールしていない場合は、GAC と BizTalk 管理データベースに異なるバージョンのアセンブリが格納されている可能性があります。  
> 
> [!IMPORTANT]
>  バージョン番号については、Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] から利用できる .NET Framework ヘルプの「アセンブリのバージョン管理」を参照してください。 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] では、.NET ポリシー ファイルの使用がサポートされません。  
  
## <a name="see-also"></a>参照  
 [BizTalk アプリケーションに Visual Studio から BizTalk アセンブリの展開](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md)   
 [BizTalk アプリケーションの展開と管理について](../core/understanding-biztalk-application-deployment-and-management.md)