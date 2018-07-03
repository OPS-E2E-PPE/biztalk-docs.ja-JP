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
ms.openlocfilehash: e1cd2db294ae0bd9e32db1a81209fe9226512e2a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996211"
---
# <a name="how-to-install-password-synchronization"></a>パスワード同期をインストールする方法
パスワード同期は、他のシングル サインオン機能と同様、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の既定のインストールではインストールされません。セットアップのときに、明示的に選択する必要があります。  
  
### <a name="to-install-password-synchronization"></a>パスワード同期をインストールするには  
  
1. BizTalk Server の CD を参照、  **\<CDRoot\>\Platforms\SSO**フォルダー。  
  
2. 実行**setup.exe**ウィザードの指示に従います。  
  
3. 選択、**パスワード同期**機能し、インストールを続行します。  
  
   外部システムとの間でパスワードの変更をやり取りするには、この他にパスワード同期アダプターが必要です。 このセクションのトピックでは、アダプターを構成する方法について説明します。  
  
   利用可能なパスワード同期アダプターについての情報は、サポート用アドレスにお問い合わせいただいても入手できます。  
  
   最後に、Active Directory で行われるパスワードの変更を取り込むため、ドメイン コントローラーに、ENTSSO パスワード同期機能に加え、パスワードの変更を取り込むコンポーネントをインストールする必要があります。  
  
   パスワードを取り込むすべてのドメイン コントローラーに、Windows Password Capture コンポーネントとパスワード変更通知サービス (PCNS) をインストールする必要があります。 これらのコンポーネントは、次の場所からインストールできます。  
  
   [http://go.microsoft.com/fwlink/?LinkId=68145](http://go.microsoft.com/fwlink/?LinkId=68145)  
  
   ドメイン コントローラーへのインストールを続行する前に、同じフォルダーに収録されている付属のドキュメントを読んでください。  
  
## <a name="see-also"></a>参照  
 [パスワード同期](../core/password-synchronization2.md)