---
title: A4SWIFT サイト グループの構成 |Microsoft Docs
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
ms.openlocfilehash: 7f19db0461fc4dc5584fa0774ba0476e3ee471b8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36969771"
---
# <a name="configuring-a4swift-site-groups"></a>A4SWIFT サイト グループの構成
Message Repair and New Submission の構成時に作成されたドキュメント ライブラリのアクセス許可をロックダウンする対応するサイトのグループを作成する必要があります。 前のセクションの例のように、A4SWIFT 管理者は MRSR サイトに移動して、次のサイト グループを設定します。  
  
- Payments_Creators  
  
- Payments_Repairers  
  
- Payments_Approvers  
  
  これらのサイト グループごとには、次のアクセス許可を適用してください。  
  
- **項目を表示します。** リスト、ドキュメント ライブラリにアイテムを表示、Web ディスカッション コメントを表示およびリストの電子メール通知を設定します。  
  
- **ページを表示します。** Web サイトでページを表示します。  
  
  支払部門のロールに参加しているユーザーごとに、新しいサイトのユーザーを作成し、そのユーザーに対応するサイトのグループに割り当てする必要があります。 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] MMC 構成中に作成されたロール。