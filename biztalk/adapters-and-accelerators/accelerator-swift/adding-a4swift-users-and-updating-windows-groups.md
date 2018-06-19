---
title: A4SWIFT のユーザーを追加して、Windows グループの更新 |Microsoft ドキュメント
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
ms.openlocfilehash: ce3fbf2f3b78b13205b43989c2b0c03909dec392
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209930"
---
# <a name="adding-a4swift-users-and-updating-windows-groups"></a>A4SWIFT のユーザーを追加して、Windows グループの更新
作成し、Message Repair and New Submission の役割用の証明書をインストールして、後に作成する必要が[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーを追加および[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]グループへのユーザーです。  
  
 **概要**  
  
 Message Repair and New Submission のユーザーを作成し、ローカルまたはドメイン アカウントを追加して[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]ユーザー グループを次のようにします。  
  
-   [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]管理コンソールで、Message Repair and New Submission のプロセスのワークフローの段階での役割があるユーザーの数を作成する必要があります。 これらのユーザーのそれぞれに個別の証明書を関連付けます。  
  
-   使用して、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]コンピューターの管理ユーティリティを確認することを作成するには、修復、各ローカル ユーザーを追加または A4SWIFT のユーザーにメッセージを承認します。  
  
-   使用して、[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]コンピューター管理ユーティリティ、BizTalk Service BizTalk Group サービスのログ名 フィールドに記載されているローカル ユーザーを追加、[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザー グループ。  
  
    > [!NOTE]
    >  詳細については[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザーとロールを参照してください[Message Repair and New Submission のロールの作成の部門と](../../adapters-and-accelerators/accelerator-swift/creating-departments-and-roles-for-message-repair-and-new-submission.md)です。  
  
### <a name="to-add-user-accounts-to-the-a4swift-users-group"></a>A4SWIFT の Users グループにユーザー アカウントを追加するには  
  
1.  をクリックして**開始**、 をポイント**すべてのプログラム**、 をポイント**管理ツール**、順にクリック**コンピューターの管理**です。  
  
2.  **コンピューターの管理**ダイアログ ボックスで、左側のウィンドウで展開**ローカル ユーザーとグループ**、クリックして**グループ**です。  
  
3.  **コンピューターの管理**ダイアログ ボックスで、右側のウィンドウでダブルクリック**A4SWIFT ユーザー**です。  
  
4.  **A4SWIFT ユーザー プロパティ**ダイアログ ボックスで、をクリックして**追加**です。  
  
5.  **ユーザー、コンピューター、またはグループ** ダイアログ ボックスで、**を選択するオブジェクト名の入力** ウィンドウで、作成、修復、検証、または、メッセージを承認したローカル ユーザーの名前を入力し、をクリックして**OK**です。  
  
6.  各ローカル ユーザーの作成、修復、検証、またはメッセージを承認するには、手順 5. を繰り返します。  
  
7.  A4SWIFT Users のプロパティ] ダイアログ ボックス [ **OK**です。  
  
8.  コンピューターの管理 ダイアログ ボックスの左側のウィンドウで、サービスとアプリケーションを展開し、サービス をクリックします。 右側のウィンドウでをクリックして**BizTalk Service BizTalk Group**です。 [ログオン方法] 列に示されたユーザーに注意してください**BizTalk Service BizTalk Group**です。  
  
9. 左側のウィンドウで、**コンピューターの管理** ダイアログ ボックスで、展開**ローカル ユーザーとグループ**、クリックして**グループ**です。 ダブルクリックして**A4SWIFT ユーザー**です。 [ログオン方法] 列で、ユーザーが表示されていることを確認してください。 **BizTalk Service BizTalk Group**の一部である、 **A4SWIFT ユーザー**グループ。 そのユーザーがいない場合は、追加、 **A4SWIFT ユーザー**グループ。  
  
10. サーバーからログオフし、再度ログオンします。