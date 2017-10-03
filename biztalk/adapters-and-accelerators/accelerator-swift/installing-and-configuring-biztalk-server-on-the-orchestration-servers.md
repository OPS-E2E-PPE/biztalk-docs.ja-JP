---
title: "インストールして、オーケストレーション サーバー上の BizTalk Server の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Server, installing on orchestration server
- orchestration server, installing BizTalk Server
ms.assetid: 72376a80-1377-4058-9478-fee668b804d0
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d872d58c72110d7af22c6d64e7d212fbee53fae9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="installing-and-configuring-biztalk-server-on-the-orchestration-servers"></a>インストールして、オーケストレーション サーバーに BizTalk Server を構成します。
インストールおよび構成する方法について説明[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]修復 新規のメッセージの発信オーケストレーションおよび FIN 修復と調整のオーケストレーションを実行するオーケストレーション サーバーとして使用します。  
  
### <a name="to-install-and-configure-biztalk-server-on-the-orchestration-server"></a>インストールして、オーケストレーション サーバー上の BizTalk Server の構成  
  
1.  カスタム インストールを実行する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]他のアプリケーションで必要な場合は、EDI、ヒューマン ワークフロー サービス (HWS)、および MRSR、以外のすべての機能を選択します。  
  
    > [!NOTE]
    >  1 台のコンピューター展開では、このコンピューターは、HTTP フロント エンド サービスと、BizTalk メッセージング サーバーを実行しているものと同じコンピューターは。  
  
2.  構成を行う[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。  
  
    > [!NOTE]
    >  BizTalk オーケストレーション サーバーを構成するときに、次のガイドラインを考慮してください。  
  
    -   このサーバーに接続するための 1 つのみのネットワーク アダプターが必要、[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]コンピューター。 パブリック HTTP フロント エンド サーバーなど、メッセージング サーバー側で別のネットワーク アダプターは必要ありませんし、これにより、インターネットまたはイントラネットとエクストラネットからのハッキングに対してセキュリティを強化します。  
  
3.  必要な追加の修正プログラムをインストール[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]インストール ガイドで使用可能とします。