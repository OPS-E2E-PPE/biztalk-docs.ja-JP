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
ms.openlocfilehash: bb758aea5910f14ff345ecd8408e52218cc6860c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65398577"
---
# <a name="upgrading-from-a-previous-version-of-sso"></a>SSO の以前のバージョンからアップグレードします。
エンタープライズ シングル サインオン機能をインストールする (たとえば、Microsoft BizTalk Server 2009) からコンピューターに展開されている以前のバージョンが既にある場合は、次の手順を完了する必要があります。  
  
1. セキュリティで保護された場所に、SSO データベースのバックアップします。  
  
2. マスタ シークレット サーバーでマスター シークレット キーのバックアップします。  
  
3. 実行して、マスター シークレット サーバーを更新[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]セットアップで選択**カスタム インストール**を選択し、**エンタープライズ シングル サインオン**します。  
  
4. 選択した後**このコンピューターで有効にするエンタープライズ シングル サインオン**、**既存の SSO システムに参加**します。  
  
   他の SSO サーバー (非マスター シークレット サーバー) を更新する必要はありません、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールします。 ただし、これらのサーバーで使用可能にする新しいエンタープライズ シングル サインオン機能を実行する場合に、上記で説明した同じ手順を使用して更新する必要があります。  
  
> [!NOTE]
>  これらの考慮事項は、Microsoft をインストールする場合にも適用[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ホスト統合 Server 2009 Enterprise Single Sign-On との既存のインストールを使用しているコンピューターをサーバーを更新します。  
  
 コンピューターに Host Integration Server をインストールするかどうか、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]が既にインストールされている、エンタープライズ シングル サインオン機能を選択しないでください。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [ホスト側開始 SSO 機能の使用](../core/using-host-initiated-sso-functionality.md)  
  
-   [SSO の処理サーバー](../core/processing-servers-for-sso.md)