---
title: SSO の以前のバージョンからのアップグレード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- upgrading, SSO
- SSO, upgrading
ms.assetid: 78b99d99-9a10-4453-9db5-ae1bacd7de50
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d12a4ee046fa7c7d835f0ddd16187e79d9d19c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979283"
---
# <a name="upgrading-from-a-previous-version-of-sso"></a>SSO の以前のバージョンからアップグレードします。
エンタープライズ シングル サインオン機能をインストールする (たとえば、Microsoft BizTalk Server 2009) からコンピューターに展開されている以前のバージョンが既にある場合は、次の手順を完了する必要があります。  
  
1. SSO データベースをセキュリティで保護された場所にバックアップします。  
  
2. マスタ シークレット サーバーにあるマスタ シークレット キーをバックアップします。  
  
3. 実行して、マスター シークレット サーバーを更新[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]セットアップで選択**カスタム インストール**を選択し、**エンタープライズ シングル サインオン**します。  
  
4. 選択した後**このコンピューターで有効にするエンタープライズ シングル サインオン**、**既存の SSO システムに参加**します。  
  
   マスタ シークレット サーバー以外の SSO サーバーについては、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストールを更新する必要はありません。 ただし、他の SSO サーバーでも新しいエンタープライズ シングル サインオン機能を使用する場合は、上記の手順を使用して SSO を更新する必要があります。  
  
> [!NOTE]
>  これは、Host Integration Server 2009 のエンタープライズ シングル サインオン機能がインストールされているコンピューターに Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールする際に、サーバーを更新する必要がある場合にも該当します。  
  
 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がインストールされているコンピューターに Host Integration Server をインストールする場合は、エンタープライズ シングル サインオン機能を選択しないでください。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ホスト側開始 SSO 機能の使用](../core/using-host-initiated-sso-functionality.md)  
  
-   [SSO の処理サーバー](../core/processing-servers-for-sso.md)