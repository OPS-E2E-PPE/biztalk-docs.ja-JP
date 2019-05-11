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
ms.openlocfilehash: 7001dae85183069b5e977276582cceef91954db1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384922"
---
# <a name="how-to-install-password-synchronization"></a><span data-ttu-id="65c35-102">パスワード同期をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="65c35-102">How to Install Password Synchronization</span></span>
<span data-ttu-id="65c35-103">その他のシングル サインオン機能と、パスワード同期がインストールされていない、既定で、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]インストールでは、し、セットアップ時に明示的に選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65c35-103">As with the other Single Sign-On features, Password Synchronization is not installed in the default [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] installation, and must be specifically selected during setup.</span></span>  
  
### <a name="to-install-password-synchronization"></a><span data-ttu-id="65c35-104">パスワード同期をインストールするには</span><span class="sxs-lookup"><span data-stu-id="65c35-104">To install Password Synchronization</span></span>  
  
1. <span data-ttu-id="65c35-105">BizTalk Server の CD を参照、  **\<CDRoot\>\Platforms\SSO**フォルダー。</span><span class="sxs-lookup"><span data-stu-id="65c35-105">On the BizTalk Server CD, browse to the **\<CDRoot\>\Platforms\SSO** folder.</span></span>  
  
2. <span data-ttu-id="65c35-106">実行**setup.exe**ウィザードの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="65c35-106">Run **setup.exe** and follow the instructions in the wizard.</span></span>  
  
3. <span data-ttu-id="65c35-107">選択、**パスワード同期**機能し、インストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="65c35-107">Select the **Password Synchronization** feature and proceed with the installation.</span></span>  
  
   <span data-ttu-id="65c35-108">さらに、パスワード同期アダプターは、外部システムにパスワードの変更を送受信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65c35-108">In addition to this, Password synchronization adapters are necessary to send and receive password changes to the external system.</span></span> <span data-ttu-id="65c35-109">このセクションのトピックでは、独自のアダプターを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="65c35-109">The topics in this section describe how to configure your own adapters.</span></span>  
  
   <span data-ttu-id="65c35-110">連絡することもできる使用可能なパスワード同期アダプターの情報を取得する別名をサポートします。</span><span class="sxs-lookup"><span data-stu-id="65c35-110">You can also contact support aliases to obtain information on available Password synchronization adapters.</span></span>  
  
   <span data-ttu-id="65c35-111">最後に、ENTSSO パスワード同期機能をインストールするだけでなく、Active Directory で行われたパスワード変更をキャプチャするコンポーネントがパスワードの変更をキャプチャするドメイン コント ローラーにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="65c35-111">Finally, to capture password changes made in Active Directory, in addition to installing the ENTSSO Password Sync feature, components need to be installed on the domain controllers to capture password changes.</span></span>  
  
   <span data-ttu-id="65c35-112">Windows Password Capture コンポーネントとのパスワード変更通知サービス (PCNS) は、パスワードをキャプチャするすべてのドメイン コント ローラーにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="65c35-112">Both the Windows Password Capture component and Password Change Notification Service (PCNS) must be installed on all domain controllers from which you will be capturing passwords.</span></span> <span data-ttu-id="65c35-113">これらのコンポーネントは、次の場所からインストールできます。</span><span class="sxs-lookup"><span data-stu-id="65c35-113">You can install these components from the following location:</span></span>  
  
   [http://go.microsoft.com/fwlink/?LinkId=68145](http://go.microsoft.com/fwlink/?LinkId=68145)  
  
   <span data-ttu-id="65c35-114">ドメイン コント ローラーのインストールを続行する前に付属のドキュメント (このフォルダーにもある) をお読みください。</span><span class="sxs-lookup"><span data-stu-id="65c35-114">Read the accompanying documentation (also located in this folder) before you proceed with the installation on the domain controller.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65c35-115">参照</span><span class="sxs-lookup"><span data-stu-id="65c35-115">See Also</span></span>  
 [<span data-ttu-id="65c35-116">パスワード同期</span><span class="sxs-lookup"><span data-stu-id="65c35-116">Password Synchronization</span></span>](../core/password-synchronization2.md)