---
title: A4SWIFT ユーザーの追加や、Windows グループの更新 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- user accounts, Windows groups
- Windows groups, user accounts
- user accounts, creating
- Windows groups, updating
- updating Windows groups
- A4SWIFT, creating user accounts
ms.assetid: ddc54457-6499-402c-9cc2-f7b17bbc255f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96bbf81638b6099f6e4d6f74704b1f94faf82679
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378674"
---
# <a name="adding-a4swift-users-and-updating-windows-groups"></a>A4SWIFT ユーザーの追加や、Windows グループの更新
作成する必要がありますを作成して、Message Repair and New Submission の役割用の証明書をインストールした後[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーを追加および[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]グループへのユーザー。  
  
 **まとめ**  
  
 Message Repair and New Submission のユーザーを作成し、ローカルまたはドメイン アカウントを追加して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]次のようにユーザーがグループ化します。  
  
- [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]管理コンソールで、Message Repair and New Submission のプロセスのワークフローの段階での役割がある多くのユーザーを作成する必要があります。 これらのユーザーごとに個別の証明書を関連付けます。  
  
- 使用して、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]コンピュータの管理ユーティリティを作成するか、修復、ユーザーごとのローカル ユーザーを追加の検証、または A4SWIFT ユーザーにメッセージを承認します。  
  
- 使用して、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]コンピューター管理ユーティリティでは、BizTalk Service BizTalk Group サービスのログとしてフィールドに一覧されているローカル ユーザーを追加、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザー グループ。  
  
  > [!NOTE]
  >  詳細については[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーとロールを参照してください[作成部門および Message Repair and New Submission のロール](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md)します。  
  
### <a name="to-add-user-accounts-to-the-a4swift-users-group"></a>A4SWIFT ユーザーのグループにユーザー アカウントを追加するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリックします**コンピュータの管理**します。  
  
2.  **コンピュータの管理**ダイアログ ボックスの左側のウィンドウで、**ローカル ユーザーとグループ**、 をクリックし、**グループ**します。  
  
3.  **コンピュータの管理** ダイアログ ボックスで、右側のウィンドウでダブルクリック**A4SWIFT ユーザー**します。  
  
4.  **A4SWIFT ユーザー プロパティ**ダイアログ ボックスで、をクリックして**追加**します。  
  
5.  **[ユーザー、コンピューター、またはグループ**] ダイアログ ボックスで、**を選択するオブジェクト名の入力**ウィンドウで、作成、修復、検証、または、メッセージの承認があるローカル ユーザーの名前を入力し、クリックして**OK**します。  
  
6.  各ローカル ユーザーの作成、修復、検証、またはメッセージを承認するには、手順 5. を繰り返します。  
  
7.  A4SWIFT ユーザーのプロパティ] ダイアログ ボックスで、[ **OK**します。  
  
8.  コンピューターの管理 ダイアログ ボックスの左側のウィンドウで、サービスとアプリケーション を展開し、サービス をクリックします。 右側のウィンドウで次のようにクリックします。 **BizTalk Service BizTalk Group**します。 [ログオン方法] 列で示されたユーザーに注意してください**BizTalk Service BizTalk Group**します。  
  
9. 左側のウィンドウで、**コンピュータの管理** ダイアログ ボックスで、展開**ローカル ユーザーとグループ**、 をクリックし、**グループ**します。 ダブルクリック**A4SWIFT ユーザー**します。 [ログオン方法] 列で、ユーザーが表示されていることを確認します。 **BizTalk Service BizTalk Group**の一部である、 **A4SWIFT ユーザー**グループ。 そうでない場合、そのユーザーを追加、 **A4SWIFT ユーザー**グループ。  
  
10. 、サーバーからログオフし、再度ログオンします。