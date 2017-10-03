---
title: "BizTalk Server での Visual Studio Team Services での自動展開の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 57f769bb-5105-43e2-9096-ed54cdf82b90
caps.latest.revision: "8"
author: tordgladnordahl
ms.author: tonordah
manager: anneta
ms.openlocfilehash: 23d79eae3bd89a572a919cfeff800178f9163796
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configure-automatic-deployment-with-visual-studio-team-services-in-biztalk-server"></a>BizTalk Server での Visual Studio Team Services の自動展開を構成します。
自動的に展開[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]Visual Studio Team Services を使用するアプリケーション。 

**以降で[!INCLUDE[bts2016_md](../includes/bts2016-md.md)] [!INCLUDE[featurepack1](../includes/featurepack1.md)]** 、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]強化された自動展開とアプリケーション ライフ サイクル管理 (ALM) のエクスペリエンスを提供します。 

ここでは、VSTS でをセットアップする方法を説明[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]を展開する、最初のアプリケーションを追加します。

## <a name="before-you-begin"></a>アンインストールの準備

* 準備ができて、Visual Studio Team Services (VSTS) アカウントがあります。 1 つを持っていない場合 [Visual Studio Team Services にサインアップする](https://www.visualstudio.com/docs/setup-admin/team-services/sign-up-for-visual-studio-team-services)です。
* BizTalk コンピューターにインストールされている VSTS エージェントがある場合、既存のエージェントは、最新のエージェントが VSTS で上書きされます。 更新する必要があります、[新しいエージェントに合うように VSTS サービス](https://www.visualstudio.com/docs/build/actions/agents/v2-windows#replace-an-agent)です。
* VSTS と自動展開はいずれかで行われる[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]グループにします。 コンピューターに Visual Studio があることを確認して、[!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)]開発ツールおよび SDK をインストールします。 参照してください、 [!INCLUDE[btsBizTalkServerNoVersion_md](../includes/btsbiztalkservernoversion-md.md)] [ハードウェアおよびソフトウェア要件](../install-and-config-guides/hardware-and-software-requirements-for-biztalk-server-2016.md)です。

## <a name="next-steps"></a>次の手順
[自動展開用 VSTS を構成します。](../core/configure-visual-studio-team-services-to-deploy-biztalk-solutions-or-projects.md)

[JSON テンプレートを構成します。](../core/configure-the-json-template-for-automatic-deployment.md)

[環境のトークンと変数を構成します。](../core/configure-environmental-tokens-and-variables-for-automatic-deployment.md)

[VSTS を BizTalk アプリケーションを追加します。](../core/add-a-biztalk-server-application-to-visual-studio-team-services.md)