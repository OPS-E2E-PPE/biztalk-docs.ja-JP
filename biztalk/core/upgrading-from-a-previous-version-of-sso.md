---
title: "SSO の以前のバージョンからのアップグレード |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- upgrading, SSO
- SSO, upgrading
ms.assetid: 78b99d99-9a10-4453-9db5-ae1bacd7de50
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bf36c33b9480c0e8658089fdc9d996b3701d7660
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="upgrading-from-a-previous-version-of-sso"></a>SSO の以前のバージョンからアップグレードします。
エンタープライズ シングル サインオン機能をインストールする (たとえば、Microsoft BizTalk Server 2009) からコンピューターに展開されている以前のバージョンが既にある場合は、次の手順を完了する必要があります。  
  
1.  SSO データベースをセキュリティで保護された場所にバックアップします。  
  
2.  マスタ シークレット サーバーにあるマスタ シークレット キーをバックアップします。  
  
3.  実行して、マスター シークレット サーバーを更新[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]セットアップを選択する**カスタム インストール**を選択し**エンタープライズ シングル サインオン**です。  
  
4.  選択した後**このコンピューターで有効にするエンタープライズ シングル サインオン****既存の SSO システムに参加**です。  
  
 マスタ シークレット サーバー以外の SSO サーバーについては、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストールを更新する必要はありません。 ただし、他の SSO サーバーでも新しいエンタープライズ シングル サインオン機能を使用する場合は、上記の手順を使用して SSO を更新する必要があります。  
  
> [!NOTE]
>  これは、Host Integration Server 2009 のエンタープライズ シングル サインオン機能がインストールされているコンピューターに Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールする際に、サーバーを更新する必要がある場合にも該当します。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がインストールされているコンピューターに Host Integration Server をインストールする場合は、エンタープライズ シングル サインオン機能を選択しないでください。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [使用してホスト側開始 SSO 機能](../core/using-host-initiated-sso-functionality.md)  
  
-   [SSO の処理サーバー](../core/processing-servers-for-sso.md)