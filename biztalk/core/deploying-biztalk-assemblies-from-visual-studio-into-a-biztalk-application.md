---
title: BizTalk アプリケーションに Visual Studio から BizTalk アセンブリの展開 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: accef4b8-acdf-4043-8fd7-2db9ea752074
caps.latest.revision: 36
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c4dcacede998ec0c921a379841e9b31389f2aa20
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007187"
---
# <a name="deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application"></a>Visual Studio から BizTalk アプリケーションへの BizTalk アセンブリの展開
デプロイおよびから BizTalk アセンブリを再デプロイ[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]BizTalk アプリケーションにします。 この処理を使用して、開発したアセンブリの機能をテストし、ハンドオフ用にパッケージすることができます。  

## <a name="overview"></a>概要  
 BizTalk アプリケーションは、BizTalk ビジネス ソリューションを構成する "アイテム" を表示して管理する手段を提供します。 アイテムに含まれる BizTalk アセンブリ (オーケストレーション、スキーマ、マップ、パイプラインなど) は、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] から [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] に展開できます。 また、アイテムには .NET アセンブリ、証明書、スクリプト、Readme ファイル、ポリシーなども含まれます。これらは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理コンソールまたは BTSTask コマンドライン ツールを使用して BizTalk アプリケーションに追加します。 その後、ソリューション開発者や IT 管理者は、アプリケーションとそのアイテムを 1 つのエンティティとして表示、パッケージ化、展開、および管理できます。 作成の詳細については、デプロイ、および、BizTalk アプリケーションの管理について[Deploying and Managing BizTalk Applications](../core/deploying-and-managing-biztalk-applications.md)します。  
  
 BizTalk アセンブリをビルドおよび展開するには、まず [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でプロジェクトを作成し、アセンブリに組み込むアイテムを作成または追加する必要があります。 [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] でソリューションを作成して、複数のプロジェクトを組み込んだ後、アセンブリをビルドし、すべてのアセンブリをまとめて同じアプリケーションまたは異なるアプリケーションに展開できます。 これらのタスクを実行する方法の詳細については、次を参照してください。 [BizTalk プロジェクトを作成する方法](../core/how-to-create-biztalk-projects.md)します。  
  
 これらの作業が完了した後は、このセクションの各トピックで説明されている手順に従って、BizTalk アセンブリのビルド、展開、および展開解除を行うことができます。  
  
- [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] プロジェクトごとに厳密な名前のアセンブリ キー ファイルを構成します。  
  
- アセンブリを簡単に再展開するための再展開オプションの構成など、プロジェクトの展開プロパティを設定します。  
  
- ソリューションに含まれる BizTalk アセンブリをビルドし、BizTalk アプリケーションに展開するには、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の展開コマンドを使用します。 または、展開コマンドを使用してアセンブリをビルドし、単一のプロジェクトに展開することもできますが、この方法はお勧めしません。  
  
- アプリケーションをテストし、必要な変更を行った後、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] の展開コマンドを使用して、アセンブリのリビルドと再展開を行います。  
  
- 必要に応じて、グローバル アセンブリ キャッシュ (GAC) にアセンブリをインストール、または GAC からアセンブリを削除します。  
  
- アセンブリを展開解除します。  
  
  BizTalk アプリケーションに 1 つ以上のアセンブリを展開した後は、アプリケーションの構成を完了し、テスト環境に展開し、さらに実稼働環境に展開できます。 詳細については、次を参照してください。 [BizTalk アプリケーション展開の開発タスク](../core/development-tasks-for-biztalk-application-deployment.md)します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [Visual Studio からアセンブリを展開する場合の動作](../core/what-happens-when-you-deploy-an-assembly-from-visual-studio.md)  
  
-   [GAC でのアセンブリのインストール](../core/assembly-installation-in-the-gac.md)  
  
-   [厳密な名前のアセンブリ キー ファイルを構成する方法](../core/how-to-configure-a-strong-name-assembly-key-file.md)  
  
-   [Visual Studio での展開のプロパティを設定する方法](../core/how-to-set-deployment-properties-in-visual-studio.md)  
  
-   [Visual Studio から BizTalk アセンブリを展開する方法](../core/how-to-deploy-a-biztalk-assembly-from-visual-studio.md)  
  
-   [Visual Studio から BizTalk アセンブリを再デプロイする方法](../core/how-to-redeploy-a-biztalk-assembly-from-visual-studio.md)  
  
-   [インストールする方法、GAC にアセンブリをアンインストールまたは](../core/how-to-install-an-assembly-in-the-gac.md)  