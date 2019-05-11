---
title: フィルターするにはパスワードを使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: eb429f8b-c301-45a3-8a4f-bbe6f2c566a3
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 22b7939c7a6e00404c9c1b4db586cc9723504aa6
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65383354"
---
# <a name="how-to-use-password-filters"></a><span data-ttu-id="dd9cc-102">パスワード フィルタを使用する方法</span><span class="sxs-lookup"><span data-stu-id="dd9cc-102">How to Use Password Filters</span></span>
<span data-ttu-id="dd9cc-103">ENTSSO パスワード同期機能は、Microsoft Windows Active Directory と Windows 以外のシステム間でパスワードを同期します。</span><span class="sxs-lookup"><span data-stu-id="dd9cc-103">The ENTSSO Password Synchronization feature synchronizes passwords between Microsoft Windows Active Directory and non-Windows systems.</span></span> <span data-ttu-id="dd9cc-104">ただし、多くの外部システムでは、Active Directory で異なる場合は、パスワード ポリシーの要件があります。</span><span class="sxs-lookup"><span data-stu-id="dd9cc-104">However, many external systems have password policy requirements which differ from those in Active Directory.</span></span> <span data-ttu-id="dd9cc-105">(たとえば、IBM システムでは大文字に変換するパスワードが必要し、8 文字に制限されています)。これにより、「最小公分母」パスワード セキュリティに限って、2 つのシステムを使用する ENTSSO が強制されます。</span><span class="sxs-lookup"><span data-stu-id="dd9cc-105">(For example, an IBM system may require a password to be upper case and limited to 8 characters.) This forces ENTSSO to use the “lowest common denominator” between the two systems, limiting password security.</span></span>  
  
 <span data-ttu-id="dd9cc-106">ENTSSO パスワード フィルタ機能は、この制限に対処します。</span><span class="sxs-lookup"><span data-stu-id="dd9cc-106">The ENTSSO Password Filter feature addresses this limitation.</span></span> <span data-ttu-id="dd9cc-107">パスワード フィルタは、定義されている追加のプロパティでパスワード同期アダプターだけです。</span><span class="sxs-lookup"><span data-stu-id="dd9cc-107">A Password Filter is merely a Password Sync Adapter with additional properties defined.</span></span> <span data-ttu-id="dd9cc-108">外部システムの条件を満たすように、パスワードをフィルタ処理をこれらの追加プロパティ (最大値または最小の長さの場合も、文字の制限など)。</span><span class="sxs-lookup"><span data-stu-id="dd9cc-108">These additional properties (such as maximum or minimum length, case, and character restrictions) serve to filter the passwords so that they meet the criteria of the external system.</span></span>  
  
 <span data-ttu-id="dd9cc-109">パスワード フィルターを作成するときにその指定されている管理者グループが自動的に SSO 管理者アカウントとして使用することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="dd9cc-109">Note that when you create a Password Filter, the Administrator group specified is automatically used as the SSO Administrators account.</span></span> <span data-ttu-id="dd9cc-110">SSO 管理者グループを変更する場合は、パスワード フィルターが新しい SSO 管理者アカウントを使用しても更新されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd9cc-110">If you change the SSO Administrator group, you will need to make sure the Password Filter is also updated with the new SSO Administrators account.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dd9cc-111">、ENTSSO システムのすべての要素と同様は、パスワード フィルターは、機密性の高い情報が含まれてし、可能なユーザーの最小数を公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dd9cc-111">As with all elements of the ENTSSO system, Password Filters contain highly sensitive information and should be exposed to the minimum number of people possible.</span></span>  
  
### <a name="to-create-a-password-filter"></a><span data-ttu-id="dd9cc-112">パスワード フィルターを作成するには</span><span class="sxs-lookup"><span data-stu-id="dd9cc-112">To Create a Password Filter</span></span>  
  
1.  <span data-ttu-id="dd9cc-113">**SSO 管理コンソール**を右クリックし、**パスワード管理**ノード、およびクリック**フィルターの作成**です。</span><span class="sxs-lookup"><span data-stu-id="dd9cc-113">In the **SSO Management Console**, right-click the **Password Management** node, and then click **Create Filter**.</span></span>  
  
     <span data-ttu-id="dd9cc-114">**パスワード フィルタ ウィザード**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dd9cc-114">The **Password Filter Wizard** appears.</span></span>  
  
2.  <span data-ttu-id="dd9cc-115">パスワード フィルターを作成するウィザードの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="dd9cc-115">Follow the directions on the Wizard to create the Password Filter.</span></span>  
  
### <a name="to-assign-an-affiliate-application-to-a-password-filter"></a><span data-ttu-id="dd9cc-116">パスワード フィルターを関連アプリケーションを割り当てる</span><span class="sxs-lookup"><span data-stu-id="dd9cc-116">To Assign an Affiliate Application to a Password Filter</span></span>  
  
1.  <span data-ttu-id="dd9cc-117">適切なフィルターを右クリックし、をクリックし、**割り当てる**.</span><span class="sxs-lookup"><span data-stu-id="dd9cc-117">Right-click the appropriate filter, and then click **Assign**….</span></span>  
  
2.  <span data-ttu-id="dd9cc-118">適切な選択**関連アプリケーション**します。</span><span class="sxs-lookup"><span data-stu-id="dd9cc-118">Select the appropriate **Affiliate Application**.</span></span>