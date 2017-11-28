---
title: "パスワード Synchronization2 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, passwords
- passwords, synchronizing [SSO]
- managing [SSO], synchronizing passwords
- Password Synchronization [SSO]
- Password Synchronization [SSO], about Password Synchronization
- SSO database, passwords
ms.assetid: 6d4970e0-ac73-4fca-ab8f-6c8a6f3a6ec0
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b9c12bc9ff5190fe0a76c92b1cfee2233b9d206a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="password-synchronization"></a><span data-ttu-id="a7d53-102">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="a7d53-102">Password Synchronization</span></span>
<span data-ttu-id="a7d53-103">パスワード同期の目的は、SSO データベースの管理を簡素化し、ユーザー ディレクトリ間でパスワードが同期された状態に保持することです。</span><span class="sxs-lookup"><span data-stu-id="a7d53-103">The purpose of Password Synchronization is to simplify administration of the SSO database, and to keep passwords in sync across user directories.</span></span>  
  
 <span data-ttu-id="a7d53-104">この 2 つの作業は、パスワード同期アダプタを使用することで行われます。このセクションの各トピックでは、このアダプタを作成および管理するためのコマンド ライン ユーティリティについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a7d53-104">These two tasks are accomplished through the use of password synchronization adapters, and the topics in this section describe the command line utility for creating and managing those adapters.</span></span>  
  
 <span data-ttu-id="a7d53-105">パスワード同期には、3 種類のサブ機能があります。</span><span class="sxs-lookup"><span data-stu-id="a7d53-105">There are three types of password synchronization sub-features.</span></span>  
  
 <span data-ttu-id="a7d53-106">最初の型が**Windows 外部から**(たとえば、Active Directory から RACF へ)。</span><span class="sxs-lookup"><span data-stu-id="a7d53-106">The first type is **Windows to External** (for example, Active Directory to RACF).</span></span> <span data-ttu-id="a7d53-107">このシナリオでは、Windows ユーザーのパスワード変更がキャプチャされ、ドメイン コントローラからパスワードの変更を受け取るよう割り当てられた、エンタープライズ SSO サーバーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="a7d53-107">In this scenario, a Windows user's password change is captured and sent to the Enterprise SSO Server assigned to receive password changes from domain controllers.</span></span> <span data-ttu-id="a7d53-108">これにより、パスワードの変更が外部システムに転送され、SSO データベースでのマッピングが、外部システムで行われた変更と同期された状態に保持されます。</span><span class="sxs-lookup"><span data-stu-id="a7d53-108">This then forwards the password change to an external system and the mapping in the SSO database is kept in sync with the change made on the external system.</span></span>  
  
 <span data-ttu-id="a7d53-109">2 番目の型は**外部から Windows の完全な同期**です。</span><span class="sxs-lookup"><span data-stu-id="a7d53-109">The second type is **External to Windows - Full synchronization**.</span></span> <span data-ttu-id="a7d53-110">このシナリオでは、パスワードが外部システムでキャプチャされ、パスワード同期用に割り当てられたエンタープライズ シングル サインオン サーバーに送信されます。その後、パスワード同期により、SSO データベースのパスワードが更新され、Active Directory の Windows ユーザーのパスワードも更新されます。</span><span class="sxs-lookup"><span data-stu-id="a7d53-110">In this scenario, a password is captured on the External system and sent to the Enterprise Single Sign-On server assigned for Password Synchronization which then updates the password in the SSO database, and also updates the Windows user's password in Active Directory.</span></span>  
  
 <span data-ttu-id="a7d53-111">3 番目の型は**Windows - 部分的な同期を外部**です。</span><span class="sxs-lookup"><span data-stu-id="a7d53-111">The third type is **External to Windows - Partial synchronization**.</span></span> <span data-ttu-id="a7d53-112">このシナリオでは、パスワードが外部システムでキャプチャされ、パスワード同期用に割り当てられたエンタープライズ シングル サインオン サーバーに送信されます。その後、パスワード同期により SSO データベースのパスワードが更新されます。</span><span class="sxs-lookup"><span data-stu-id="a7d53-112">In this scenario a password is captured on the External system and sent to the Enterprise Single Sign-On server assigned for Password Synchronization which then updates the password in the SSO database.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a7d53-113">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a7d53-113">In This Section</span></span>  
  
-   [<span data-ttu-id="a7d53-114">パスワード同期をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="a7d53-114">How to Install Password Synchronization</span></span>](../core/how-to-install-password-synchronization.md)  
  
-   [<span data-ttu-id="a7d53-115">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="a7d53-115">How to Administer Password Synchronization</span></span>](../core/how-to-administer-password-synchronization.md)  
  
-   [<span data-ttu-id="a7d53-116">パスワード同期を構成する方法</span><span class="sxs-lookup"><span data-stu-id="a7d53-116">How to Configure Password Synchronization</span></span>](../core/how-to-configure-password-synchronization.md)  
  
-   [<span data-ttu-id="a7d53-117">パスワード同期を管理する方法</span><span class="sxs-lookup"><span data-stu-id="a7d53-117">How to Manage Password Synchronization</span></span>](../core/how-to-manage-password-synchronization.md)