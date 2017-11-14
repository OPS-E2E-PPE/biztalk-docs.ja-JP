---
title: "Visual Studio Team Services での自動展開の構成 |Microsoft ドキュメント"
description: "Vsts アプリケーション ライフ サイクル管理を使用して、別の BizTalk 環境にアプリケーションを展開する BizTalk Feature Pack をインストールします。"
ms.custom: 
ms.date: 11/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57f769bb-5105-43e2-9096-ed54cdf82b90
caps.latest.revision: "8"
author: tordgladnordahl
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04a7d2b2430a5dc57403fc179fa1c1859d3a82b3
ms.sourcegitcommit: a0165ec2f1e8b58545638666b7bfa2bf440036fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2017
---
# <a name="configure-automatic-deployment-with-visual-studio-team-services-in-biztalk-server"></a>BizTalk Server での Visual Studio Team Services の自動展開を構成します。

## <a name="overview"></a>概要

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]強化された自動展開とアプリケーション ライフ サイクル管理 (ALM) のエクスペリエンスを提供します。 

Visual Studio Team Services を使用して、自動的に展開できます[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]別の BizTalk 環境にアプリケーションです。 

通常は 2 つのロールです。

- BizTalk 開発者は、アプリケーションを作成し、それをローカルでビルドします。 次に、アプリケーションを Git または Team Foundation バージョン管理を確認します。
- VSTS 管理者は、ビルドとリリースの定義を作成し、(Dev、UAT、実稼働) の別の環境に BizTalk アプリケーションに展開します。

VSTS を初めて使用する場合は、このチュートリアルが困難な可能性があります。 Git、クローン作成、変更のプッシュなどに関する一定の知識は必要です。 

VSTS をセットアップする方法を説明[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]を展開する、最初のアプリケーションを追加します。 参照することをお勧め、 [VSTS ガイダンス](https://docs.microsoft.com/vsts/user-guide/)、VSTS UI が変更されました。 

## <a name="before-you-begin"></a>アンインストールの準備

* 準備ができて、Visual Studio Team Services (VSTS) アカウントがあります。 1 つを持っていない場合 [Visual Studio Team Services にサインアップする](https://www.visualstudio.com/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services)です。
* BizTalk コンピューターにインストールされている VSTS エージェントがある場合、既存のエージェントは、最新のエージェントが VSTS で上書きされます。 更新する必要があります、[新しいエージェントに合うように VSTS サービス](https://www.visualstudio.com/docs/build/actions/agents/v2-windows#replace-an-agent)です。
* VSTS と自動展開はいずれかで行われる[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]グループにします。 コンピューターに Visual Studio があることを確認して、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]開発ツールおよび SDK をインストールします。 参照してください、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] [ハードウェアおよびソフトウェア要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)です。

## <a name="prerequisites"></a>前提条件

* インストール[機能パック 1](https://www.microsoft.com/download/details.aspx?id=55100)で、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* 一部のエクスペリエンスと知識 VSTS 内の定義の作成と操作をします。 VSTS をまったく新しい場合は、これら優れたリソースがあります。 

  [Visual Studio Team Services の概要](https://www.visualstudio.com/docs/overview)  
  [初心者の CI/CD](https://www.visualstudio.com/docs/build/get-started/ci-cd-part-1)

## <a name="get-started"></a>作業を開始します。
[手順 1: アプリケーション プロジェクトの追加 & .json テンプレートの更新](feature-pack-add-application-project.md)  

[手順 2: VSTS トークンを作成するし、ビルド エージェントをインストール](feature-pack-create-vsts-token.md)

[手順 3: ビルドの作成し、定義のリリース](feature-pack-add-build-release-definitions.md)

[環境のトークンと変数を構成します。](configure-environmental-tokens-and-variables-for-automatic-deployment.md)