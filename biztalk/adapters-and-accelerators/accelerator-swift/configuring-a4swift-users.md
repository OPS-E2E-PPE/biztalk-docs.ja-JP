---
title: A4SWIFT ユーザーの構成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security, user accounts
- creating, user accounts
- user accounts, creating
ms.assetid: 45dcbece-ec8d-410a-8320-79bfbc4c779d
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b75a3e95c836f8a577543b43319e6abe49a96c42
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005259"
---
# <a name="configuring-a4swift-users"></a>A4SWIFT ユーザーの構成
インストール中に[!INCLUDE[A4SWIFT_CurrentVersion_FirstRef](../../includes/a4swift-currentversion-firstref-md.md)]、A4SWIFT 構成プログラムが既定取引先のプロファイルと、契約を作成し、BizTalk Server を登録します。 また、A4SWIFT には、Message Repair and New Submission のコンポーネントで使用されるドキュメント ライブラリが作成されます。  
  
 A4SWIFT のインストール中に次のドキュメント フォルダーを作成します。  
  
- 送信トレイ ドキュメント ライブラリ  
  
- テンプレート ドキュメント ライブラリ  
  
- 未解析のドキュメント ライブラリ  
  
- 新しい SWIFT MT メッセージ ドキュメント ライブラリ  
  
- 新しい SWIFT MX メッセージ ドキュメント ライブラリ  
  
  各部門を作成すると、A4SWIFT 管理者は、対応する部門のサイト グループを手動で設定する必要があり、A4SWIFT がロールを定義します。 各部門/ロールでは、プロファイルの Web Client(PWC) によって自動的に作成された受信トレイがあります。  
  
  A4SWIFT セットアップ構成プログラムが完了した後、A4SWIFT 管理者は、組織の各部門のワークフローを構成します。 プロファイル Web クライアントを通じて、Message Repair and New Submission の構成中に、対応する受信トレイは、部門/ロールの組み合わせごとに作成されます。 たとえば、PWC 構成中に、A4SWIFT 管理者は支払いをという名前の部署を作成しますを支払いと呼ばれる部門に作成者、Repairers、および承認者のロールを割り当てます。 MRSR サイトのドキュメント ライブラリは、次の表の例で示すように、受信トレイの名前で作成されます。  
  
|部門名|ロール名|受信トレイ名|  
|---------------------|---------------|----------------|  
|支払い|作成者|Payments_Creator|  
|支払い|Repairers|Payments_Repairers|  
|支払い|承認者|Payments_Approvers|