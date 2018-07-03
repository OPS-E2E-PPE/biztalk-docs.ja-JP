---
title: SSO の以前のバージョンからのアップグレード |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- upgrading, SSO
- SSO, upgrading
ms.assetid: 78b99d99-9a10-4453-9db5-ae1bacd7de50
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9d12a4ee046fa7c7d835f0ddd16187e79d9d19c5
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36979283"
---
# <a name="upgrading-from-a-previous-version-of-sso"></a><span data-ttu-id="a01b5-102">SSO の以前のバージョンからアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="a01b5-102">Upgrading from a Previous Version of SSO</span></span>
<span data-ttu-id="a01b5-103">エンタープライズ シングル サインオン機能をインストールする (たとえば、Microsoft BizTalk Server 2009) からコンピューターに展開されている以前のバージョンが既にある場合は、次の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a01b5-103">If you are installing the Enterprise Single Sign-on feature and you already have a previous version deployed on your computer (for example, from Microsoft BizTalk Server 2009), you must complete the steps below.</span></span>  
  
1. <span data-ttu-id="a01b5-104">SSO データベースをセキュリティで保護された場所にバックアップします。</span><span class="sxs-lookup"><span data-stu-id="a01b5-104">Back up the SSO database to a secure location</span></span>  
  
2. <span data-ttu-id="a01b5-105">マスタ シークレット サーバーにあるマスタ シークレット キーをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="a01b5-105">Back up the master secret key on the master secret server</span></span>  
  
3. <span data-ttu-id="a01b5-106">実行して、マスター シークレット サーバーを更新[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]セットアップで選択**カスタム インストール**を選択し、**エンタープライズ シングル サインオン**します。</span><span class="sxs-lookup"><span data-stu-id="a01b5-106">Update the master secret server by running [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] setup, choosing **Custom Installation**, and then selecting **Enterprise Single Sign-On**.</span></span>  
  
4. <span data-ttu-id="a01b5-107">選択した後**このコンピューターで有効にするエンタープライズ シングル サインオン**、**既存の SSO システムに参加**します。</span><span class="sxs-lookup"><span data-stu-id="a01b5-107">After selecting **Enable Enterprise Single Sign-on on this computer**, select **Join an existing SSO system**.</span></span>  
  
   <span data-ttu-id="a01b5-108">マスタ シークレット サーバー以外の SSO サーバーについては、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] のインストールを更新する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="a01b5-108">It is not necessary to update the other SSO servers (non-master secret servers) from your [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation.</span></span> <span data-ttu-id="a01b5-109">ただし、他の SSO サーバーでも新しいエンタープライズ シングル サインオン機能を使用する場合は、上記の手順を使用して SSO を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a01b5-109">However, if you want the new Enterprise Single Sign-On features to be available on those servers, you must update them by using the same procedure outlined above.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a01b5-110">これは、Host Integration Server 2009 のエンタープライズ シングル サインオン機能がインストールされているコンピューターに Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] をインストールする際に、サーバーを更新する必要がある場合にも該当します。</span><span class="sxs-lookup"><span data-stu-id="a01b5-110">These considerations also apply if you are installing Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] on a computer with an existing installation of Host Integration Server 2009 Enterprise Single Sign-On, and you want to update the servers.</span></span>  
  
 <span data-ttu-id="a01b5-111">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] がインストールされているコンピューターに Host Integration Server をインストールする場合は、エンタープライズ シングル サインオン機能を選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="a01b5-111">If you are installing Host Integration Server on a computer where [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] is already installed, do not select the Enterprise Single Sign-On feature.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a01b5-112">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a01b5-112">In This Section</span></span>  
  
-   [<span data-ttu-id="a01b5-113">ホスト側開始 SSO 機能の使用</span><span class="sxs-lookup"><span data-stu-id="a01b5-113">Using Host Initiated SSO Functionality</span></span>](../core/using-host-initiated-sso-functionality.md)  
  
-   [<span data-ttu-id="a01b5-114">SSO の処理サーバー</span><span class="sxs-lookup"><span data-stu-id="a01b5-114">Processing Servers for SSO</span></span>](../core/processing-servers-for-sso.md)