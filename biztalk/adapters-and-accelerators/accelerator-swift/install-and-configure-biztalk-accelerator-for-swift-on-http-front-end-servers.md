---
title: インストールと BizTalk Accelerator を HTTP フロント エンド サーバー上の SWIFT の構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- HTTP server, installing BizTalk Accelerator for SWIFT
- BizTalk Accelerator for SWIFT, installing on HTTP server
ms.assetid: 1deaa5f7-9da2-4d4b-8367-2d6900065839
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9cf35a971dbc3dad14568f880b058c1ff131a087
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377361"
---
# <a name="installing-and-configuring-biztalk-accelerator-for-swift-on-http-front-end-servers"></a>インストールと BizTalk Accelerator を HTTP フロント エンド サーバー上の SWIFT の構成
このセクションは、インストールして構成する方法を説明します[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]HTTP フロント エンド サーバー。 これらのサーバーは主に、SWIFT ネットワークとの通信に使用します。  

### <a name="to-install-and-configure-biztalk-accelerator-for-swift-on-the-http-front-end-server"></a>インストールして構成 BizTalk Accelerator for SWIFT HTTP フロント エンド サーバーに  

1. カスタム インストール実行[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]します。 インストール、 **MRSR**と**Message Repair and New Submission の Web コンポーネント**機能します。  

   > [!NOTE]
   >  インストールが完了したら、構成ウィザードが開始されます。  

2. Microsoft[!INCLUDE[A4SWIFT_CurrentVersion_abbrev](../../includes/a4swift-currentversion-abbrev-md.md)]構成コンソールで、構成**MCRR**と**WebService**します。  

3. フォルダーに web.config ファイルを開き、Web サーバーで、構成ウィザードの完了後に\<*ドライブ*\>: \Program Files\Microsoft [!INCLUDE[btaA4SWIFTNoVersion](../../includes/btaa4swiftnoversion-md.md)]\Service\ メモ帳でします。 "Authorization"を検索します。 **承認**セクションで、A4SWIFT ユーザーのグループの名前にロールの値を設定します。
