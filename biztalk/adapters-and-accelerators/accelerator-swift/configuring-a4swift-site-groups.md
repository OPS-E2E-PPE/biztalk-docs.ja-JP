---
title: A4SWIFT サイト グループの構成 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- site groups, creating
- creating, site groups
- security, user accounts
- user accounts, site groups
- site groups, user accounts
ms.assetid: ec2f3efe-439a-4018-ad94-5ab0fb2808ee
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0070f10819ebbde18cdeab9c3bd534ca74bfbcd9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209010"
---
# <a name="configuring-a4swift-site-groups"></a>A4SWIFT サイト グループの構成
Message Repair and New Submission の構成時に作成されたドキュメント ライブラリのアクセス許可をロックダウンする対応するサイト グループを作成する必要があります。 前のセクションの例のように、A4SWIFT 管理者は MRSR サイトに移動して、次のサイト グループを設定します。  
  
-   Payments_Creators  
  
-   Payments_Repairers  
  
-   Payments_Approvers  
  
 これらのサイト グループの列ごとには、次のアクセス許可を適用してください。  
  
-   **項目を表示します。** ドキュメント ライブラリのドキュメント、リストの項目を表示では、Web ディスカッションのコメントを表示し、リストの電子メール通知を設定します。  
  
-   **ページを表示します。** Web サイト内のページを表示します。  
  
 各ユーザーの支払い部門では、役割に参加している、する必要があります、新しいサイトのユーザーを作成し、そのユーザーに対応するサイト グループを割り当てます[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]MMC の構成時に作成されたロールです。