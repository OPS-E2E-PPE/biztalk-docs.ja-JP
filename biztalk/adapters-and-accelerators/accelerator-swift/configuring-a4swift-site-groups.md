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
ms.openlocfilehash: e56eb836ffde957244b5ca80e6d7491f9e8c207c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378955"
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