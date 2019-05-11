---
title: パスワード Synchronization2 |Microsoft Docs
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
ms.openlocfilehash: 4ade05264bd65fc43c240ba377f4e99f26167bf3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65394984"
---
# <a name="password-synchronization"></a>パスワード同期
パスワード同期の目的は、SSO データベースの管理を簡素化し、ユーザー ディレクトリ間のパスワードの同期を維持するには。  
  
 これら 2 つのタスクは、パスワード同期アダプタを使用して行い、このセクションのトピックでは、作成およびこれらのアダプターを管理するコマンド ライン ユーティリティを記述します。  
  
 パスワード同期のサブ機能の 3 種類があります。  
  
 1 つ目は**外部 Windows** (たとえば、RACF に Active Directory)。 このシナリオでは Windows ユーザーのパスワードの変更がキャプチャされ、ドメイン コント ローラーからパスワードの変更を受信する割り当てられたエンタープライズ SSO サーバーに送信します。 この、外部システムにパスワードの変更を転送し、SSO データベース内のマッピングは、外部システムで行われた変更での同期を維持します。  
  
 2 つ目は**Windows の完全な同期を外部**します。 パスワードの外部システムでキャプチャされ、SSO データベースにパスワードを更新し、アクティブな Windows ユーザーのパスワードを更新するためのパスワード同期用に割り当てられたエンタープライズ シングル サインオン サーバーに送信されるこのシナリオでディレクトリ。  
  
 3 番目の型は**Windows - 部分の同期を外部**します。 このシナリオでは、パスワードが外部システムでキャプチャし、SSO データベースのパスワードを更新するパスワードの同期に割り当てられたエンタープライズ シングル サインオン サーバーに送信します。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [パスワード同期をインストールする方法](../core/how-to-install-password-synchronization.md)  
  
-   [パスワード同期を管理する方法](../core/how-to-administer-password-synchronization.md)  
  
-   [パスワード同期を構成する方法](../core/how-to-configure-password-synchronization.md)  
  
-   [パスワード同期を管理する方法](../core/how-to-manage-password-synchronization.md)