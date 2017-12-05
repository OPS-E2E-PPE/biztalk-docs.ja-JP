---
title: "パスワード同期をインストールする方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- installing, Password Synchronization [SSO]
- Password Synchronization [SSO], installing
ms.assetid: 8ace0401-b759-4ea3-91a0-be2aa8b5a5a4
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3a6a3f93e600a8e68581f09af8fcdbc77ed57af
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-install-password-synchronization"></a><span data-ttu-id="e09e3-102">パスワード同期をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="e09e3-102">How to Install Password Synchronization</span></span>
<span data-ttu-id="e09e3-103">パスワード同期は、他のシングル サインオン機能と同様、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の既定のインストールではインストールされません。セットアップのときに、明示的に選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e09e3-103">As with the other Single Sign-On features, Password Synchronization is not installed in the default [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation, and must be specifically selected during setup.</span></span>  
  
### <a name="to-install-password-synchronization"></a><span data-ttu-id="e09e3-104">パスワード同期をインストールするには</span><span class="sxs-lookup"><span data-stu-id="e09e3-104">To install Password Synchronization</span></span>  
  
1.  <span data-ttu-id="e09e3-105">BizTalk Server の CD を参照して、  **\<CDRoot\>\Platforms\SSO**フォルダーです。</span><span class="sxs-lookup"><span data-stu-id="e09e3-105">On the BizTalk Server CD, browse to the **\<CDRoot\>\Platforms\SSO** folder.</span></span>  
  
2.  <span data-ttu-id="e09e3-106">実行**setup.exe**ウィザードの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="e09e3-106">Run **setup.exe** and follow the instructions in the wizard.</span></span>  
  
3.  <span data-ttu-id="e09e3-107">選択、**パスワード同期**機能し、インストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="e09e3-107">Select the **Password Synchronization** feature and proceed with the installation.</span></span>  
  
 <span data-ttu-id="e09e3-108">外部システムとの間でパスワードの変更をやり取りするには、この他にパスワード同期アダプターが必要です。</span><span class="sxs-lookup"><span data-stu-id="e09e3-108">In addition to this, Password synchronization adapters are necessary to send and receive password changes to the external system.</span></span> <span data-ttu-id="e09e3-109">このセクションのトピックでは、アダプターを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e09e3-109">The topics in this section describe how to configure your own adapters.</span></span>  
  
 <span data-ttu-id="e09e3-110">利用可能なパスワード同期アダプターについての情報は、サポート用アドレスにお問い合わせいただいても入手できます。</span><span class="sxs-lookup"><span data-stu-id="e09e3-110">You can also contact support aliases to obtain information on available Password synchronization adapters.</span></span>  
  
 <span data-ttu-id="e09e3-111">最後に、Active Directory で行われるパスワードの変更を取り込むため、ドメイン コントローラーに、ENTSSO パスワード同期機能に加え、パスワードの変更を取り込むコンポーネントをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e09e3-111">Finally, to capture password changes made in Active Directory, in addition to installing the ENTSSO Password Sync feature, components need to be installed on the domain controllers to capture password changes.</span></span>  
  
 <span data-ttu-id="e09e3-112">パスワードを取り込むすべてのドメイン コントローラーに、Windows Password Capture コンポーネントとパスワード変更通知サービス (PCNS) をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e09e3-112">Both the Windows Password Capture component and Password Change Notification Service (PCNS) must be installed on all domain controllers from which you will be capturing passwords.</span></span> <span data-ttu-id="e09e3-113">これらのコンポーネントは、次の場所からインストールできます。</span><span class="sxs-lookup"><span data-stu-id="e09e3-113">You can install these components from the following location:</span></span>  
  
 [<span data-ttu-id="e09e3-114">http://go.microsoft.com/fwlink/?LinkId=68145</span><span class="sxs-lookup"><span data-stu-id="e09e3-114">http://go.microsoft.com/fwlink/?LinkId=68145</span></span>](http://go.microsoft.com/fwlink/?LinkId=68145)  
  
 <span data-ttu-id="e09e3-115">ドメイン コントローラーへのインストールを続行する前に、同じフォルダーに収録されている付属のドキュメントを読んでください。</span><span class="sxs-lookup"><span data-stu-id="e09e3-115">Read the accompanying documentation (also located in this folder) before you proceed with the installation on the domain controller.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e09e3-116">参照</span><span class="sxs-lookup"><span data-stu-id="e09e3-116">See Also</span></span>  
 [<span data-ttu-id="e09e3-117">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="e09e3-117">Password Synchronization</span></span>](../core/password-synchronization2.md)