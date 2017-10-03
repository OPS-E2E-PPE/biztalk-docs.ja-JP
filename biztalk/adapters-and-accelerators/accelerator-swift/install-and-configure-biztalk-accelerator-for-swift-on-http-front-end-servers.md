---
title: "インストールと BizTalk Accelerator を HTTP フロント エンド サーバーに SWIFT の構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- HTTP server, installing BizTalk Accelerator for SWIFT
- BizTalk Accelerator for SWIFT, installing on HTTP server
ms.assetid: 1deaa5f7-9da2-4d4b-8367-2d6900065839
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: fe0a320f9f60f72975faf903c1355b8730840b26
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="installing-and-configuring-biztalk-accelerator-for-swift-on-http-front-end-servers"></a>インストールと BizTalk Accelerator を HTTP フロント エンド サーバーに SWIFT の構成
インストールおよび構成する方法について説明[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]HTTP フロント エンド サーバーにします。 これらのサーバーは主に SWIFT ネットワークとの通信に使用します。  
  
### <a name="to-install-and-configure-biztalk-accelerator-for-swift-on-the-http-front-end-server"></a>インストールでおよび構成する BizTalk Accelerator for SWIFT HTTP フロント エンド サーバー  
  
1.  カスタム インストールを実行[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]です。 インストール、 **MRSR**と**Message Repair and New Submission の Web コンポーネント**機能します。  
  
    > [!NOTE]
    >  インストールが完了したら、構成ウィザードを開始します。  
  
2.  Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]構成コンソールで、構成**MCRR**と**WebService**です。  
  
3.  Web サーバーで、構成ウィザードの完了後に、フォルダーに web.config ファイルを開きます。 \<*ドライブ*>: \Program Files\Microsoft[!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]メモ帳で \Service\ です。 "Authorization"を検索します。 **承認**セクションで、ロール値 A4SWIFT users グループの名前を設定します。