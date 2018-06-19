---
title: ホスト側開始 SSO |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- host initiated SSO
- SSO, SSO database
- SSO, host initiated
- managing [SSO], host intitiated
ms.assetid: 492f730d-08ec-47d6-a88b-0d373bd8912b
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 136ed2555410187a98960d6671c0c960aeebdd04
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246362"
---
# <a name="host-initiated-sso"></a><span data-ttu-id="b03c9-102">ホスト側開始 SSO</span><span class="sxs-lookup"><span data-stu-id="b03c9-102">Host Initiated SSO</span></span>
<span data-ttu-id="b03c9-103">ホスト側開始のシングル サインオンを使用すると、ホスト システムからの要求で Windows システム上のリソースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b03c9-103">Host initiated Single Sign-On enables a request from the host system to access a resource on a Windows system.</span></span> <span data-ttu-id="b03c9-104">このホスト システム (たとえば、RACF アカウント) は、Windows 以外の環境の、Windows 以外のユーザーのコンテキストに存在します。</span><span class="sxs-lookup"><span data-stu-id="b03c9-104">The host system (for example, a RACF account) exists in a non-Windows environment and under the context of a non-Windows user.</span></span> <span data-ttu-id="b03c9-105">このようなアクセスを可能にするために、シングル サインオンの資格情報ストアによってホスト アカウントが Windows アカウントにマップされます。</span><span class="sxs-lookup"><span data-stu-id="b03c9-105">The Single Sign-On Credential Store maps host accounts to Windows accounts, enabling this access.</span></span>  
  
 <span data-ttu-id="b03c9-106">次のトピックでは、ホスト側開始 SSO に固有の構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="b03c9-106">The following topics describe configuration specific to Host initiated SSO.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b03c9-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="b03c9-107">In This Section</span></span>  
  
-   [<span data-ttu-id="b03c9-108">側開始 SSO のホストの要件を構成する方法</span><span class="sxs-lookup"><span data-stu-id="b03c9-108">How to Configure Requirements for Host Initiated SSO</span></span>](../core/how-to-configure-requirements-for-host-initiated-sso.md)  
  
-   [<span data-ttu-id="b03c9-109">側開始 SSO を有効にし、ホストを無効にする方法</span><span class="sxs-lookup"><span data-stu-id="b03c9-109">How to Enable and Disable Host Initiated SSO</span></span>](../core/how-to-enable-and-disable-host-initiated-sso.md)  
  
-   [<span data-ttu-id="b03c9-110">ホスト側開始 SSO 関連アプリケーションを作成する方法</span><span class="sxs-lookup"><span data-stu-id="b03c9-110">How to Create Affiliate Applications for Host Initiated SSO</span></span>](../core/how-to-create-affiliate-applications-for-host-initiated-sso.md)  
  
-   [<span data-ttu-id="b03c9-111">ホストのパスワードを検証する側開始 SSO</span><span class="sxs-lookup"><span data-stu-id="b03c9-111">Validating Passwords for Host Initiated SSO</span></span>](../core/validating-passwords-for-host-initiated-sso.md)  
  
-   [<span data-ttu-id="b03c9-112">側開始 SSO のホストのユーザー マッピングを管理する方法</span><span class="sxs-lookup"><span data-stu-id="b03c9-112">How to Manage User Mappings for Host Initiated SSO</span></span>](../core/how-to-manage-user-mappings-for-host-initiated-sso.md)  
  
-   [<span data-ttu-id="b03c9-113">側開始 SSO のホストで、トレース ユーティリティを使用する方法</span><span class="sxs-lookup"><span data-stu-id="b03c9-113">How to Use the Trace Utility in Host Initiated SSO</span></span>](../core/how-to-use-the-trace-utility-in-host-initiated-sso.md)