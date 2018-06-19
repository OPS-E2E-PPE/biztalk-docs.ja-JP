---
title: フィルターするにはパスワードを使用する方法 |Microsoft ドキュメント
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
ms.openlocfilehash: 3ad35e2c3bec5b2ece69911b8de8c7fd13c9b790
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22255938"
---
# <a name="how-to-use-password-filters"></a><span data-ttu-id="4c976-102">パスワード フィルタを使用する方法</span><span class="sxs-lookup"><span data-stu-id="4c976-102">How to Use Password Filters</span></span>
<span data-ttu-id="4c976-103">ENTSSO パスワード同期機能は、Microsoft Windows Active Directory と Windows 以外のシステムのパスワードを同期します。</span><span class="sxs-lookup"><span data-stu-id="4c976-103">The ENTSSO Password Synchronization feature synchronizes passwords between Microsoft Windows Active Directory and non-Windows systems.</span></span> <span data-ttu-id="4c976-104">しかし、多くの外部システムは、Active Directory とは異なるパスワード ポリシー要件を備えています</span><span class="sxs-lookup"><span data-stu-id="4c976-104">However, many external systems have password policy requirements which differ from those in Active Directory.</span></span> <span data-ttu-id="4c976-105">(たとえば、IBM システムでは、パスワードは 8 文字以内の大文字で指定する必要があります)。このため、パスワード セキュリティに限って、ENTSSO では 2 つのシステム間の "最小限の共通要件" を使用します。</span><span class="sxs-lookup"><span data-stu-id="4c976-105">(For example, an IBM system may require a password to be upper case and limited to 8 characters.) This forces ENTSSO to use the “lowest common denominator” between the two systems, limiting password security.</span></span>  
  
 <span data-ttu-id="4c976-106">ENTSSO パスワード フィルタ機能は、この制限事項に対応しています。</span><span class="sxs-lookup"><span data-stu-id="4c976-106">The ENTSSO Password Filter feature addresses this limitation.</span></span> <span data-ttu-id="4c976-107">パスワード フィルタは単なるパスワード同期アダプタで、いくつかのプロパティが追加で定義されています。</span><span class="sxs-lookup"><span data-stu-id="4c976-107">A Password Filter is merely a Password Sync Adapter with additional properties defined.</span></span> <span data-ttu-id="4c976-108">これらの付加的なプロパティ (最大長、最小長、大文字/小文字、文字制限など) により、外部システムの基準を満たすようにパスワードのフィルタ処理を実行します。</span><span class="sxs-lookup"><span data-stu-id="4c976-108">These additional properties (such as maximum or minimum length, case, and character restrictions) serve to filter the passwords so that they meet the criteria of the external system.</span></span>  
  
 <span data-ttu-id="4c976-109">パスワード フィルターを作成するときに指定されている管理者グループに自動的としてを使用する SSO 管理者アカウントに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4c976-109">Note that when you create a Password Filter, the Administrator group specified is automatically used as the SSO Administrators account.</span></span> <span data-ttu-id="4c976-110">SSO 管理者グループを変更すると、新しい SSO 管理者アカウントに応じてパスワード フィルタも更新されるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c976-110">If you change the SSO Administrator group, you will need to make sure the Password Filter is also updated with the new SSO Administrators account.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4c976-111">ENTSSO システムのすべての要素と同様に、パスワード フィルタには機密性の高い情報が含まれており、この情報を公開するのは必要最小限の担当者に抑えることが求められます。</span><span class="sxs-lookup"><span data-stu-id="4c976-111">As with all elements of the ENTSSO system, Password Filters contain highly sensitive information and should be exposed to the minimum number of people possible.</span></span>  
  
### <a name="to-create-a-password-filter"></a><span data-ttu-id="4c976-112">パスワード フィルタを作成するには</span><span class="sxs-lookup"><span data-stu-id="4c976-112">To Create a Password Filter</span></span>  
  
1.  <span data-ttu-id="4c976-113">**SSO 管理コンソール**を右クリックし、**パスワード管理**ノードをクリックして**フィルターの作成**です。</span><span class="sxs-lookup"><span data-stu-id="4c976-113">In the **SSO Management Console**, right-click the **Password Management** node, and then click **Create Filter**.</span></span>  
  
     <span data-ttu-id="4c976-114">**パスワード フィルタ ウィザード**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4c976-114">The **Password Filter Wizard** appears.</span></span>  
  
2.  <span data-ttu-id="4c976-115">ウィザードの指示に従って、パスワード フィルタを作成します。</span><span class="sxs-lookup"><span data-stu-id="4c976-115">Follow the directions on the Wizard to create the Password Filter.</span></span>  
  
### <a name="to-assign-an-affiliate-application-to-a-password-filter"></a><span data-ttu-id="4c976-116">パスワード フィルタに関連アプリケーションを割り当てるには</span><span class="sxs-lookup"><span data-stu-id="4c976-116">To Assign an Affiliate Application to a Password Filter</span></span>  
  
1.  <span data-ttu-id="4c976-117">適切なフィルターを右クリックし、をクリックして**割り当てる**しています.</span><span class="sxs-lookup"><span data-stu-id="4c976-117">Right-click the appropriate filter, and then click **Assign**….</span></span>  
  
2.  <span data-ttu-id="4c976-118">適切な選択**関連アプリケーション**です。</span><span class="sxs-lookup"><span data-stu-id="4c976-118">Select the appropriate **Affiliate Application**.</span></span>