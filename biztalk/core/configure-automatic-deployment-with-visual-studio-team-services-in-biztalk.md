---
title: Visual Studio Team Services での自動展開の構成 |Microsoft Docs
description: VSTS とアプリケーション ライフ サイクル管理を使用して、さまざまな BizTalk 環境にアプリケーションをデプロイする BizTalk Feature Pack のインストールします。
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
ms.openlocfilehash: 99d321e4f5987fe642b8a2dd4babc2c67093aad9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65356444"
---
# <a name="configure-automatic-deployment-with-visual-studio-team-services-in-biztalk-server"></a>BizTalk Server での Visual Studio Team Services での自動展開を構成します。

## <a name="overview"></a>概要

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]強化された自動展開とアプリケーション ライフ サイクル管理 (ALM) のエクスペリエンスを提供します。 

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)]Feature Pack 2**、この機能が強化されました。

* Visual Studio で、設定、**アプリケーション名**BizTalk アプリケーションの
* エージェント ベースの展開だけでなく、使用することも[配置グループ](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/index)複数のサーバーに BizTalk アプリケーションをデプロイするには
* リリース タスクで、BizTalk アプリケーションをインストールおよび展開パッケージに、BizTalk 管理コンピューターと、パスを入力します。

Visual Studio Team Services を使用して、自動的に展開できます[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]さまざまな BizTalk 環境へのアプリケーション。 

通常、ある 2 つのロール関連します。

- BizTalk 開発者は、アプリケーションを作成し、ローカルで構築します。 次に、Git または Team Foundation バージョン管理にアプリケーションを確認します。
- VSTS 管理者は、ビルドとリリースの定義を作成し、さまざまな環境 (開発、UAT、運用環境) への BizTalk アプリケーションをデプロイします。

VSTS を初めて使用する、このチュートリアルが困難な可能性があります。 Git、クローン作成、変更のプッシュなどのいくつかの理解は必要です。 

使用した VSTS をセットアップする方法を紹介[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]、展開する最初のアプリケーションを追加します。 参照することをお勧め、 [VSTS ガイダンス](https://docs.microsoft.com/vsts/user-guide/)VSTS UI を変更すると、します。 

## <a name="before-you-begin"></a>アンインストールの準備

* 準備ができて、Visual Studio Team Services (VSTS) アカウントがあります。 ないでしょうか。 [Visual Studio Team Services にサインアップ](https://www.visualstudio.com/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services)します。
* BizTalk コンピューターにインストールされている VSTS エージェント既にある場合、既存のエージェントは、VSTS の最新のエージェントで上書きされます。 更新する必要があります、[新しいエージェントの連携を VSTS サービス](https://www.visualstudio.com/docs/build/actions/agents/v2-windows#replace-an-agent)します。
* 1 つで VSTS を使用した自動展開を行う機能パック 1、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]グループ。 コンピューターに Visual Studio があることを確認して、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]開発者用ツールと SDK をインストールします。 参照してください、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] [ハードウェアおよびソフトウェア要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)します。
* Feature Pack 2 と VSTS を使用した自動展開の実行に使用できますを使用して[配置グループ](https://docs.microsoft.com/vsts/build-release/concepts/definitions/release/deployment-groups/howto-deployment-groups)します。 配置グループを使用して、配置グループ内の複数の BizTalk Server アプリケーションをデプロイできます。

## <a name="prerequisites"></a>前提条件

* インストール[Feature Pack 2](https://aka.ms/bts2016fp2)で、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]
* 一部のエクスペリエンスと VSTS での定義の作成と操作の情報が提供します。 VSTS にまったく新しい場合は、これらの優れたリソースがあります。 

  [Visual Studio Team Services の概要](https://www.visualstudio.com/docs/overview)  
  [初心者の CI/CD](https://www.visualstudio.com/docs/build/get-started/ci-cd-part-1)

## <a name="get-started"></a>作業開始
[ステップ 1: アプリケーションのプロジェクトと更新プログラムの .json テンプレートを追加します。](feature-pack-add-application-project.md)  

[手順 2:VSTS トークンの作成し、ビルド エージェントのインストール](feature-pack-create-vsts-token.md)

[ステップ 3:ビルドとリリース定義を作成します。](feature-pack-add-build-release-definitions.md)

[環境トークンと変数を構成します。](configure-environmental-tokens-and-variables-for-automatic-deployment.md)