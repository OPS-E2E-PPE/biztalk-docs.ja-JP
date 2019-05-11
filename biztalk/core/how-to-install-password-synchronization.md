---
title: パスワード同期をインストールする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, Password Synchronization [SSO]
- Password Synchronization [SSO], installing
ms.assetid: 8ace0401-b759-4ea3-91a0-be2aa8b5a5a4
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7001dae85183069b5e977276582cceef91954db1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384922"
---
# <a name="how-to-install-password-synchronization"></a>パスワード同期をインストールする方法
その他のシングル サインオン機能と、パスワード同期がインストールされていない、既定で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールでは、し、セットアップ時に明示的に選択する必要があります。  
  
### <a name="to-install-password-synchronization"></a>パスワード同期をインストールするには  
  
1. BizTalk Server の CD を参照、  **\<CDRoot\>\Platforms\SSO**フォルダー。  
  
2. 実行**setup.exe**ウィザードの指示に従います。  
  
3. 選択、**パスワード同期**機能し、インストールを続行します。  
  
   さらに、パスワード同期アダプターは、外部システムにパスワードの変更を送受信する必要があります。 このセクションのトピックでは、独自のアダプターを構成する方法について説明します。  
  
   連絡することもできる使用可能なパスワード同期アダプターの情報を取得する別名をサポートします。  
  
   最後に、ENTSSO パスワード同期機能をインストールするだけでなく、Active Directory で行われたパスワード変更をキャプチャするコンポーネントがパスワードの変更をキャプチャするドメイン コント ローラーにインストールする必要があります。  
  
   Windows Password Capture コンポーネントとのパスワード変更通知サービス (PCNS) は、パスワードをキャプチャするすべてのドメイン コント ローラーにインストールされている必要があります。 これらのコンポーネントは、次の場所からインストールできます。  
  
   [http://go.microsoft.com/fwlink/?LinkId=68145](http://go.microsoft.com/fwlink/?LinkId=68145)  
  
   ドメイン コント ローラーのインストールを続行する前に付属のドキュメント (このフォルダーにもある) をお読みください。  
  
## <a name="see-also"></a>参照  
 [パスワード同期](../core/password-synchronization2.md)