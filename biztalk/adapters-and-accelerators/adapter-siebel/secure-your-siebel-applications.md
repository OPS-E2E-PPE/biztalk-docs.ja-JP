---
title: Siebel アプリケーションのセキュリティ保護 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- security and protection
- data protection
ms.assetid: 8977cbd3-0025-48d4-8203-8e9e72ea7d26
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3b597120de91b6a09fdc26b90a2cb357cdc7dd1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22221970"
---
# <a name="secure-your-siebel-applications"></a><span data-ttu-id="90b35-102">Siebel アプリケーションのセキュリティ保護します。</span><span class="sxs-lookup"><span data-stu-id="90b35-102">Secure your Siebel applications</span></span>
<span data-ttu-id="90b35-103">Siebel システムには、多くの場合、お客様のアカウント詳細などの機密性の高いビジネス情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="90b35-103">The Siebel system often contains sensitive business information such as customer account details.</span></span> <span data-ttu-id="90b35-104">使用するアプリケーション、[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]にアクセスして、この情報を変更するいずれかのローカルまたは分散ネットワーク経由で公開される可能性が誤ってに不正のアクターによってアクセスする作業はに対して保護して、中にデータをセキュリティで保護しない限り、転送します。</span><span class="sxs-lookup"><span data-stu-id="90b35-104">Applications that use the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] to access and modify this information either locally or across a distributed network might inadvertently expose it to access by unauthorized actors, unless efforts are made to protect and secure the data during transmission.</span></span> <span data-ttu-id="90b35-105">データ保護およびセキュリティは、通常と考えるは次の用語で。</span><span class="sxs-lookup"><span data-stu-id="90b35-105">Data protection and security are usually thought of in the following terms:</span></span>  
  
-   <span data-ttu-id="90b35-106">*承認*要求者の身元に基づいて、リソースへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="90b35-106">*Authorization* controls access to a resource based on the identity of the requester.</span></span>  
  
-   <span data-ttu-id="90b35-107">*認証*要求者の身元を確認するためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="90b35-107">*Authentication* provides mechanisms for verifying the identity of a requester.</span></span>  
  
-   <span data-ttu-id="90b35-108">*データの機密性*暗号化によるデータのプライバシーを保護するためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="90b35-108">*Data confidentiality* provides mechanisms for protecting the privacy of data through encryption.</span></span>  
  
-   <span data-ttu-id="90b35-109">*データの整合性*受信側が、データがされていないことを確認することができます、データのデジタル署名するメカニズムを提供、転送中に変更します。</span><span class="sxs-lookup"><span data-stu-id="90b35-109">*Data integrity* provides mechanisms to digitally sign data, so that the receiver can ensure that the data has not been altered in-transit.</span></span>  
  
 <span data-ttu-id="90b35-110">問題になるもう 1 つの重要な領域は、ユーザー名パスワード資格情報を提供する、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="90b35-110">Another important area of concern is the user-name password credentials that you supply to the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="90b35-111">アダプターでは、これらの資格情報を使用して、Siebel システムへの接続を開きます。</span><span class="sxs-lookup"><span data-stu-id="90b35-111">The adapter uses these credentials to open connections to the Siebel system.</span></span> <span data-ttu-id="90b35-112">これらの資格情報を指定する接続 URI です。ただし、ユーザー名とパスワードはクリア テキストであるため、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]より安全な方法でこれらの資格情報を指定するのに使用できる代替のメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="90b35-112">These credentials can be supplied in the connection URI; however, because the user name and password are clear text, the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] provides alternative methods that you can use to supply these credentials in a more secure manner.</span></span>  
  
 <span data-ttu-id="90b35-113">このセクションのトピックでは、向上に役立つガイドラインで開発したソリューションのセキュリティを提供、[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="90b35-113">The topics in this section provide guidelines to help you better secure the solutions that you develop with the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="90b35-114">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="90b35-114">In This Section</span></span>  
  
-   [<span data-ttu-id="90b35-115">Siebel システムとアダプター間のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="90b35-115">Security between the Siebel system and the adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/security-between-the-siebel-system-and-the-adapter.md)
  
-   [<span data-ttu-id="90b35-116">Siebel アダプターと BizTalk Server でのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="90b35-116">Security with Siebel adapter and BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-siebel/security-with-siebel-adapter-and-biztalk-server.md)
  
-   [<span data-ttu-id="90b35-117">Siebel アダプターをセキュリティで保護された使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="90b35-117">Secure programming with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/secure-programming-with-the-siebel-adapter.md)
  
-   [<span data-ttu-id="90b35-118">Siebel アダプターをセキュリティで保護するベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="90b35-118">Best practices to secure the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/best-practices-to-secure-the-siebel-adapter.md)