---
title: "A4SWIFT のユーザーの構成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- security, user accounts
- creating, user accounts
- user accounts, creating
ms.assetid: 45dcbece-ec8d-410a-8320-79bfbc4c779d
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79c3b63cd77bb34545f4c4093796310aa7720563
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-a4swift-users"></a>A4SWIFT のユーザーを構成します。
インストール中に[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]、A4SWIFT 構成プログラムが既定の取引パートナー プロファイルやアグリーメントが作成され、BizTalk Server を登録します。 A4SWIFT には、Message Repair and New Submission のコンポーネントで使用されるドキュメント ライブラリも作成されます。  
  
 A4SWIFT のインストール時に、次のドキュメント フォルダーを作成します。  
  
-   送信トレイ ドキュメント ライブラリ  
  
-   テンプレート ドキュメント ライブラリ  
  
-   未解析のドキュメント ライブラリ  
  
-   新しい SWIFT MT メッセージ ドキュメント ライブラリ  
  
-   新しい SWIFT MX メッセージ ドキュメント ライブラリ  
  
 各部署を作成すると、A4SWIFT 管理者は、対応する部門のグループをサイトを手動で設定する必要があり、A4SWIFT がロールを定義します。 各部門/ロールには、受信トレイ プロファイル Web Client(PWC) によって自動的に作成します。  
  
 A4SWIFT セットアップ構成プログラムが完了した後、A4SWIFT 管理者は、組織の各部門のワークフローを構成します。 プロファイル Web クライアントを通じて、Message Repair and New Submission の構成時に、対応する受信トレイは、部門またはロールの組み合わせごとに作成されます。 など、PWC 構成中に、A4SWIFT 管理者は支払いをという名前の部門を作成し、し、支払と呼ばれる部門に作成者、Repairers、および承認者の役割を割り当てます。 MRSR サイト上のドキュメント ライブラリは、次の表の例に示すように、受信トレイ名で作成されます。  
  
|部門名|ロール名|受信トレイ名|  
|---------------------|---------------|----------------|  
|支払い|作成者|Payments_Creator|  
|支払い|Repairers|Payments_Repairers|  
|支払い|承認者|Payments_Approvers|