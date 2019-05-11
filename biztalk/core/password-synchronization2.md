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
# <a name="password-synchronization"></a><span data-ttu-id="481e0-102">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="481e0-102">Password Synchronization</span></span>
<span data-ttu-id="481e0-103">パスワード同期の目的は、SSO データベースの管理を簡素化し、ユーザー ディレクトリ間のパスワードの同期を維持するには。</span><span class="sxs-lookup"><span data-stu-id="481e0-103">The purpose of Password Synchronization is to simplify administration of the SSO database, and to keep passwords in sync across user directories.</span></span>  
  
 <span data-ttu-id="481e0-104">これら 2 つのタスクは、パスワード同期アダプタを使用して行い、このセクションのトピックでは、作成およびこれらのアダプターを管理するコマンド ライン ユーティリティを記述します。</span><span class="sxs-lookup"><span data-stu-id="481e0-104">These two tasks are accomplished through the use of password synchronization adapters, and the topics in this section describe the command line utility for creating and managing those adapters.</span></span>  
  
 <span data-ttu-id="481e0-105">パスワード同期のサブ機能の 3 種類があります。</span><span class="sxs-lookup"><span data-stu-id="481e0-105">There are three types of password synchronization sub-features.</span></span>  
  
 <span data-ttu-id="481e0-106">1 つ目は**外部 Windows** (たとえば、RACF に Active Directory)。</span><span class="sxs-lookup"><span data-stu-id="481e0-106">The first type is **Windows to External** (for example, Active Directory to RACF).</span></span> <span data-ttu-id="481e0-107">このシナリオでは Windows ユーザーのパスワードの変更がキャプチャされ、ドメイン コント ローラーからパスワードの変更を受信する割り当てられたエンタープライズ SSO サーバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="481e0-107">In this scenario, a Windows user's password change is captured and sent to the Enterprise SSO Server assigned to receive password changes from domain controllers.</span></span> <span data-ttu-id="481e0-108">この、外部システムにパスワードの変更を転送し、SSO データベース内のマッピングは、外部システムで行われた変更での同期を維持します。</span><span class="sxs-lookup"><span data-stu-id="481e0-108">This then forwards the password change to an external system and the mapping in the SSO database is kept in sync with the change made on the external system.</span></span>  
  
 <span data-ttu-id="481e0-109">2 つ目は**Windows の完全な同期を外部**します。</span><span class="sxs-lookup"><span data-stu-id="481e0-109">The second type is **External to Windows - Full synchronization**.</span></span> <span data-ttu-id="481e0-110">パスワードの外部システムでキャプチャされ、SSO データベースにパスワードを更新し、アクティブな Windows ユーザーのパスワードを更新するためのパスワード同期用に割り当てられたエンタープライズ シングル サインオン サーバーに送信されるこのシナリオでディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="481e0-110">In this scenario, a password is captured on the External system and sent to the Enterprise Single Sign-On server assigned for Password Synchronization which then updates the password in the SSO database, and also updates the Windows user's password in Active Directory.</span></span>  
  
 <span data-ttu-id="481e0-111">3 番目の型は**Windows - 部分の同期を外部**します。</span><span class="sxs-lookup"><span data-stu-id="481e0-111">The third type is **External to Windows - Partial synchronization**.</span></span> <span data-ttu-id="481e0-112">このシナリオでは、パスワードが外部システムでキャプチャし、SSO データベースのパスワードを更新するパスワードの同期に割り当てられたエンタープライズ シングル サインオン サーバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="481e0-112">In this scenario a password is captured on the External system and sent to the Enterprise Single Sign-On server assigned for Password Synchronization which then updates the password in the SSO database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="481e0-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="481e0-113">In This Section</span></span>  
  
-   [<span data-ttu-id="481e0-114">パスワード同期をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="481e0-114">How to Install Password Synchronization</span></span>](../core/how-to-install-password-synchronization.md)  
  
-   [<span data-ttu-id="481e0-115">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="481e0-115">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)  
  
-   [<span data-ttu-id="481e0-116">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="481e0-116">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="481e0-117">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="481e0-117">How to Manage Password Synchronization</span></span>](../core/how-to-manage-password-synchronization.md)