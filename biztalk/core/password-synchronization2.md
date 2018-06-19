---
title: パスワード Synchronization2 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, passwords
- passwords, synchronizing [SSO]
- managing [SSO], synchronizing passwords
- Password Synchronization [SSO]
- Password Synchronization [SSO], about Password Synchronization
- SSO database, passwords
ms.assetid: 6d4970e0-ac73-4fca-ab8f-6c8a6f3a6ec0
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9c12bc9ff5190fe0a76c92b1cfee2233b9d206a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22264362"
---
# <a name="password-synchronization"></a>パスワード同期
パスワード同期の目的は、SSO データベースの管理を簡素化し、ユーザー ディレクトリ間でパスワードが同期された状態に保持することです。  
  
 この 2 つの作業は、パスワード同期アダプタを使用することで行われます。このセクションの各トピックでは、このアダプタを作成および管理するためのコマンド ライン ユーティリティについて説明します。  
  
 パスワード同期には、3 種類のサブ機能があります。  
  
 最初の型が**Windows 外部から**(たとえば、Active Directory から RACF へ)。 このシナリオでは、Windows ユーザーのパスワード変更がキャプチャされ、ドメイン コントローラからパスワードの変更を受け取るよう割り当てられた、エンタープライズ SSO サーバーに送信されます。 これにより、パスワードの変更が外部システムに転送され、SSO データベースでのマッピングが、外部システムで行われた変更と同期された状態に保持されます。  
  
 2 番目の型は**外部から Windows の完全な同期**です。 このシナリオでは、パスワードが外部システムでキャプチャされ、パスワード同期用に割り当てられたエンタープライズ シングル サインオン サーバーに送信されます。その後、パスワード同期により、SSO データベースのパスワードが更新され、Active Directory の Windows ユーザーのパスワードも更新されます。  
  
 3 番目の型は**Windows - 部分的な同期を外部**です。 このシナリオでは、パスワードが外部システムでキャプチャされ、パスワード同期用に割り当てられたエンタープライズ シングル サインオン サーバーに送信されます。その後、パスワード同期により SSO データベースのパスワードが更新されます。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [パスワード同期をインストールする方法](../core/how-to-install-password-synchronization.md)  
  
-   [パスワード同期を管理する方法](../core/how-to-administer-password-synchronization.md)  
  
-   [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  
  
-   [パスワード同期を管理する方法](../core/how-to-manage-password-synchronization.md)