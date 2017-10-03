---
title: "インストールして、メッセージング サーバー上の BizTalk Server の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- BizTalk Server, installing on BizTalk Messaging servers
- BizTalk Server, configuring
- BizTalk Messaging servers, configuring BizTalk Server
- BizTalk Messaging servers, installing BizTalk Server
ms.assetid: 8aaa1b97-90f0-4317-9403-ac8b5b9f80e3
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2db4b3d5ff34a724b8b37a08f0bf60807d31a2b2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="installing-and-configuring-biztalk-server-on-the-messaging-server"></a>インストールして、メッセージング サーバー上の BizTalk Server の構成
インストールおよび構成する方法について説明[!INCLUDE[btsBizTalkServer2006r3](../../includes/btsbiztalkserver2006r3-md.md)]SWIFT ネットワークに接続するために、メッセージング サーバーとして使用します。  
  
### <a name="to-install-and-configure-biztalk-server-on-the-messaging-server"></a>インストールして、メッセージング サーバー上の BizTalk Server を構成するには  
  
1.  カスタム インストールを実行する[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]他のアプリケーションで必要な場合は、EDI、ヒューマン ワークフロー サービス (HWS)、および MRSR サイト以外のすべての機能を選択します。  
  
    > [!NOTE]
    >  1 台のコンピューター展開でこのコンピューターは、HTTP フロント エンド サービスを実行しているものと同じコンピューターに注意してください。  
  
2.  構成を行う[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]です。  
  
    > [!NOTE]
    >  インストールしないメッセージがキューをインストールするため、 [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] MSMQT と呼ばれる MSMQ のバージョン。 MSMQT の詳細については、MSDN Web サイトで BizTalk メッセージ キュー アダプター (MSMQT) 構成を参照してください。 [http://go.microsoft.com/fwlink/?LinkID=48875](http://go.microsoft.com/fwlink/?LinkID=48875)です。  
  
3.  必要な追加の修正プログラムをインストール[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]インストール ガイドで使用可能とします。 このパブリケーションの時に、必要な修正プログラムはありません。