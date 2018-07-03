---
title: パスワード同期をインストールする方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- installing, Password Synchronization [SSO]
- Password Synchronization [SSO], installing
ms.assetid: 8ace0401-b759-4ea3-91a0-be2aa8b5a5a4
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e1cd2db294ae0bd9e32db1a81209fe9226512e2a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36996211"
---
# <a name="how-to-install-password-synchronization"></a><span data-ttu-id="6baa1-102">パスワード同期をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="6baa1-102">How to Install Password Synchronization</span></span>
<span data-ttu-id="6baa1-103">パスワード同期は、他のシングル サインオン機能と同様、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] の既定のインストールではインストールされません。セットアップのときに、明示的に選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6baa1-103">As with the other Single Sign-On features, Password Synchronization is not installed in the default [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation, and must be specifically selected during setup.</span></span>  
  
### <a name="to-install-password-synchronization"></a><span data-ttu-id="6baa1-104">パスワード同期をインストールするには</span><span class="sxs-lookup"><span data-stu-id="6baa1-104">To install Password Synchronization</span></span>  
  
1. <span data-ttu-id="6baa1-105">BizTalk Server の CD を参照、  **\<CDRoot\>\Platforms\SSO**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="6baa1-105">On the BizTalk Server CD, browse to the **\<CDRoot\>\Platforms\SSO** folder.</span></span>  
  
2. <span data-ttu-id="6baa1-106">実行**setup.exe**ウィザードの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="6baa1-106">Run **setup.exe** and follow the instructions in the wizard.</span></span>  
  
3. <span data-ttu-id="6baa1-107">選択、**パスワード同期**機能し、インストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="6baa1-107">Select the **Password Synchronization** feature and proceed with the installation.</span></span>  
  
   <span data-ttu-id="6baa1-108">外部システムとの間でパスワードの変更をやり取りするには、この他にパスワード同期アダプターが必要です。</span><span class="sxs-lookup"><span data-stu-id="6baa1-108">In addition to this, Password synchronization adapters are necessary to send and receive password changes to the external system.</span></span> <span data-ttu-id="6baa1-109">このセクションのトピックでは、アダプターを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6baa1-109">The topics in this section describe how to configure your own adapters.</span></span>  
  
   <span data-ttu-id="6baa1-110">利用可能なパスワード同期アダプターについての情報は、サポート用アドレスにお問い合わせいただいても入手できます。</span><span class="sxs-lookup"><span data-stu-id="6baa1-110">You can also contact support aliases to obtain information on available Password synchronization adapters.</span></span>  
  
   <span data-ttu-id="6baa1-111">最後に、Active Directory で行われるパスワードの変更を取り込むため、ドメイン コントローラーに、ENTSSO パスワード同期機能に加え、パスワードの変更を取り込むコンポーネントをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6baa1-111">Finally, to capture password changes made in Active Directory, in addition to installing the ENTSSO Password Sync feature, components need to be installed on the domain controllers to capture password changes.</span></span>  
  
   <span data-ttu-id="6baa1-112">パスワードを取り込むすべてのドメイン コントローラーに、Windows Password Capture コンポーネントとパスワード変更通知サービス (PCNS) をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6baa1-112">Both the Windows Password Capture component and Password Change Notification Service (PCNS) must be installed on all domain controllers from which you will be capturing passwords.</span></span> <span data-ttu-id="6baa1-113">これらのコンポーネントは、次の場所からインストールできます。</span><span class="sxs-lookup"><span data-stu-id="6baa1-113">You can install these components from the following location:</span></span>  
  
   [http://go.microsoft.com/fwlink/?LinkId=68145](http://go.microsoft.com/fwlink/?LinkId=68145)  
  
   <span data-ttu-id="6baa1-114">ドメイン コントローラーへのインストールを続行する前に、同じフォルダーに収録されている付属のドキュメントを読んでください。</span><span class="sxs-lookup"><span data-stu-id="6baa1-114">Read the accompanying documentation (also located in this folder) before you proceed with the installation on the domain controller.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6baa1-115">参照</span><span class="sxs-lookup"><span data-stu-id="6baa1-115">See Also</span></span>  
 [<span data-ttu-id="6baa1-116">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="6baa1-116">Password Synchronization</span></span>](../core/password-synchronization2.md)