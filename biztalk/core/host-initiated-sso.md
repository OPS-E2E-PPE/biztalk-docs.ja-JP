---
title: ホスト側開始 SSO |Microsoft Docs
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
ms.openlocfilehash: 007a880a4068a30bbed73ebd4b3a310027d2e2a7
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387543"
---
# <a name="host-initiated-sso"></a><span data-ttu-id="8a047-102">ホスト側開始 SSO</span><span class="sxs-lookup"><span data-stu-id="8a047-102">Host Initiated SSO</span></span>
<span data-ttu-id="8a047-103">ホストは、シングル サインオンできるように Windows システム上のリソースにアクセスするには、ホスト システムから要求を開始します。</span><span class="sxs-lookup"><span data-stu-id="8a047-103">Host initiated Single Sign-On enables a request from the host system to access a resource on a Windows system.</span></span> <span data-ttu-id="8a047-104">ホスト システム (たとえば、RACF アカウント) は、Windows 以外の環境では Windows 以外のユーザーのコンテキストで存在します。</span><span class="sxs-lookup"><span data-stu-id="8a047-104">The host system (for example, a RACF account) exists in a non-Windows environment and under the context of a non-Windows user.</span></span> <span data-ttu-id="8a047-105">シングル サインオンの資格情報ストアは、このアクセスを有効にする Windows アカウントにホストのアカウントをマップします。</span><span class="sxs-lookup"><span data-stu-id="8a047-105">The Single Sign-On Credential Store maps host accounts to Windows accounts, enabling this access.</span></span>  
  
 <span data-ttu-id="8a047-106">次のトピックでは、構成を記述する固有のホスト側開始 SSO。</span><span class="sxs-lookup"><span data-stu-id="8a047-106">The following topics describe configuration specific to Host initiated SSO.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8a047-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="8a047-107">In This Section</span></span>  
  
-   [<span data-ttu-id="8a047-108">側開始 SSO のホストの要件を構成する方法</span><span class="sxs-lookup"><span data-stu-id="8a047-108">How to Configure Requirements for Host Initiated SSO</span></span>](../core/how-to-configure-requirements-for-host-initiated-sso.md)  
  
-   [<span data-ttu-id="8a047-109">側開始 SSO を有効にし、ホストを無効にする方法</span><span class="sxs-lookup"><span data-stu-id="8a047-109">How to Enable and Disable Host Initiated SSO</span></span>](../core/how-to-enable-and-disable-host-initiated-sso.md)  
  
-   [<span data-ttu-id="8a047-110">ホスト側開始 SSO 関連アプリケーションを作成する方法</span><span class="sxs-lookup"><span data-stu-id="8a047-110">How to Create Affiliate Applications for Host Initiated SSO</span></span>](../core/how-to-create-affiliate-applications-for-host-initiated-sso.md)  
  
-   [<span data-ttu-id="8a047-111">ホスト側開始 SSO のパスワードの検証</span><span class="sxs-lookup"><span data-stu-id="8a047-111">Validating Passwords for Host Initiated SSO</span></span>](../core/validating-passwords-for-host-initiated-sso.md)  
  
-   [<span data-ttu-id="8a047-112">側開始 SSO のホストのユーザー マッピングを管理する方法</span><span class="sxs-lookup"><span data-stu-id="8a047-112">How to Manage User Mappings for Host Initiated SSO</span></span>](../core/how-to-manage-user-mappings-for-host-initiated-sso.md)  
  
-   [<span data-ttu-id="8a047-113">側開始 SSO のホストで Trace ユーティリティを使用する方法</span><span class="sxs-lookup"><span data-stu-id="8a047-113">How to Use the Trace Utility in Host Initiated SSO</span></span>](../core/how-to-use-the-trace-utility-in-host-initiated-sso.md)