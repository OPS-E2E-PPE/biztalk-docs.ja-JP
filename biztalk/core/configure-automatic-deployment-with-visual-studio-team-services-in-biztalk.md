---
title: Visual Studio Team Services での自動展開の構成 |Microsoft ドキュメント
description: Vsts アプリケーション ライフ サイクル管理を使用して、別の BizTalk 環境にアプリケーションを展開する BizTalk Feature Pack をインストールします。
ms.custom: ''
ms.date: 11/20/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 57f769bb-5105-43e2-9096-ed54cdf82b90
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d135960143fed33d1ce4847c681f5b1134489b65
ms.sourcegitcommit: 3fd1c85d9dc2ce7b77da75a5c2087cc48cfcbe50
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/17/2018
ms.locfileid: "25497883"
---
# <a name="configure-automatic-deployment-with-visual-studio-team-services-in-biztalk-server"></a>BizTalk Server での Visual Studio Team Services の自動展開を構成します。

## <a name="overview"></a>概要

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]強化された自動展開とアプリケーション ライフ サイクル管理 (ALM) のエクスペリエンスを提供します。 

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]Feature Pack 2**、この機能を改良しました。

* Visual Studio 内で、設定、**アプリケーション名**BizTalk アプリケーションの
* エージェント ベースの展開を使用して、に加えて使用することも[展開グループ](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index)複数のサーバーに、BizTalk アプリケーションを展開するには
* リリース タスクで、BizTalk アプリケーションをインストールおよび展開パッケージに、BizTalk 管理コンピューターとパスを入力してください。

Visual Studio Team Services を使用して、自動的に展開できます[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]別の BizTalk 環境にアプリケーションです。 

通常は 2 つのロールです。

- BizTalk 開発者は、アプリケーションを作成し、それをローカルでビルドします。 次に、アプリケーションを Git または Team Foundation バージョン管理を確認します。
- VSTS 管理者は、ビルドとリリースの定義を作成し、(Dev、UAT、実稼働) の別の環境に BizTalk アプリケーションに展開します。

VSTS を初めて使用する場合は、このチュートリアルが困難な可能性があります。 Git、クローン作成、変更のプッシュなどに関する一定の知識は必要です。 

VSTS をセットアップする方法を説明[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]を展開する、最初のアプリケーションを追加します。 参照することをお勧め、 [VSTS ガイダンス](https://docs.microsoft.com/vsts/user-guide/)、VSTS UI が変更されました。 

## <a name="before-you-begin"></a>アンインストールの準備

* 準備ができて、Visual Studio Team Services (VSTS) アカウントがあります。 1 つを持っていない場合 [Visual Studio Team Services にサインアップする](https://www.visualstudio.com/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services)です。
* BizTalk コンピューターにインストールされている VSTS エージェントがある場合、既存のエージェントは、最新のエージェントが VSTS で上書きされます。 更新する必要があります、[新しいエージェントに合うように VSTS サービス](https://www.visualstudio.com/docs/build/actions/agents/v2-windows#replace-an-agent)です。
* 機能パック 1 では、VSTS で自動展開がいずれかで行われる[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]グループにします。 コンピューターに Visual Studio があることを確認して、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]開発ツールおよび SDK をインストールします。 参照してください、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] [ハードウェアおよびソフトウェア要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)です。
* VSTS を自動配置の行われる Feature Pack 2 を使用して[展開グループ](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/howto-deployment-groups)です。 展開グループを使用して、展開グループ内の複数の BizTalk サーバーにアプリケーションを展開できます。

## <a name="prerequisites"></a>前提条件

* インストール[Feature Pack 2](https://aka.ms/bts2016fp2)で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* 一部のエクスペリエンスと知識 VSTS 内の定義の作成と操作をします。 VSTS をまったく新しい場合は、これら優れたリソースがあります。 

  [Visual Studio Team Services の概要](https://www.visualstudio.com/docs/overview)  
  [初心者の CI/CD](https://www.visualstudio.com/docs/build/get-started/ci-cd-part-1)

## <a name="get-started"></a>概要します。
[手順 1: アプリケーション プロジェクトの追加および.json テンプレートの更新](feature-pack-add-application-project.md)  

[手順 2: VSTS トークンの作成およびビルド エージェントのインストール](feature-pack-create-vsts-token.md)

[手順 3: ビルドの作成し、定義のリリース](feature-pack-add-build-release-definitions.md)

[環境のトークンと変数を構成します。](configure-environmental-tokens-and-variables-for-automatic-deployment.md)