---
title: インストールして、オーケストレーション サーバーに BizTalk Server の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- BizTalk Server, installing on orchestration server
- orchestration server, installing BizTalk Server
ms.assetid: 72376a80-1377-4058-9478-fee668b804d0
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4b1883199408b503cdbd79b276257bec604ab60
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377725"
---
# <a name="installing-and-configuring-biztalk-server-on-the-orchestration-servers"></a>インストールして、オーケストレーション サーバーに BizTalk Server を構成します。
このセクションでは、インストールして、メッセージの修復]、[新しい送信オーケストレーションおよび FIN 修復と調整のオーケストレーションを実行するため、オーケストレーション サーバーとして使用する BizTalk Server を構成する方法について説明します。  

### <a name="to-install-and-configure-biztalk-server-on-the-orchestration-server"></a>インストールして、オーケストレーション サーバーに BizTalk Server を構成するには  

1. カスタム インストール実行[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]他のアプリケーションで必要な場合は、EDI、ヒューマン ワークフロー サービス (HWS) および MRSR、以外のすべての機能を選択します。  

   > [!NOTE]
   >  1 台のコンピューターの展開では、このコンピューターは、HTTP フロント エンド サービスと、BizTalk メッセージング サーバーを実行しているものと同じコンピューターは。  

2. 構成を行う[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]します。  

   > [!NOTE]
   >  BizTalk オーケストレーション サーバーを構成するときに、次のガイドラインを考慮してください。  

   - このサーバーに接続するネットワーク アダプターを 1 つだけが必要です、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]コンピューター。 HTTP フロント エンド サーバーなど、メッセージング サーバーでは、パブリックにある別のネットワーク アダプターは必要ありませんし、これにより、インターネットまたはイントラネットとエクストラネットからのハッキングに対してセキュリティを強化します。  

3. 必要な他の修正プログラムをインストール[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]インストール ガイドで利用可能な。
