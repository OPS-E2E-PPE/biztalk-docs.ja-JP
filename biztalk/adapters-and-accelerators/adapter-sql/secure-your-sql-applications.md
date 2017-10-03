---
title: "SQL アプリケーションのセキュリティ保護 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4b182593-fcca-4ebc-a2fd-7684b84cfb15
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d631bc3ad87e9a8ec8ac51850b7dbe1eb244c140
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="secure-your-sql-applications"></a><span data-ttu-id="58747-102">SQL アプリケーションのセキュリティ保護します。</span><span class="sxs-lookup"><span data-stu-id="58747-102">Secure your SQL applications</span></span>
## <a name="overview"></a><span data-ttu-id="58747-103">概要</span><span class="sxs-lookup"><span data-stu-id="58747-103">Overview</span></span>
<span data-ttu-id="58747-104">SQL Server データベースは、多くの場合、お客様のアカウント詳細などの機密性の高いビジネス情報を含めます。</span><span class="sxs-lookup"><span data-stu-id="58747-104">SQL Server databases often contain sensitive business information such as customer account details.</span></span> <span data-ttu-id="58747-105">使用するアプリケーション、[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]にアクセスして、この情報を変更するいずれかのローカルまたは分散ネットワーク経由で公開される可能性が誤ってに不正のアクターによってアクセスする作業はに対して保護して、中にデータをセキュリティで保護しない限り、転送します。</span><span class="sxs-lookup"><span data-stu-id="58747-105">Applications that use the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] to access and modify this information either locally or across a distributed network might inadvertently expose it to access by unauthorized actors, unless efforts are made to protect and secure the data during transmission.</span></span> <span data-ttu-id="58747-106">データ保護およびセキュリティは、通常と考えるは次の用語で。</span><span class="sxs-lookup"><span data-stu-id="58747-106">Data protection and security are usually thought of in the following terms:</span></span>  
  
-   <span data-ttu-id="58747-107">*承認*要求者の身元に基づいて、リソースへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="58747-107">*Authorization* controls access to a resource based on the identity of the requestor.</span></span>  
  
-   <span data-ttu-id="58747-108">*認証*要求者の身元を確認するためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="58747-108">*Authentication* provides mechanisms for verifying the identity of a requestor.</span></span>  
  
-   <span data-ttu-id="58747-109">*データの機密性*暗号化によるデータのプライバシーを保護するためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="58747-109">*Data confidentiality* provides mechanisms for protecting the privacy of data through encryption.</span></span>  
  
-   <span data-ttu-id="58747-110">*データの整合性*受信側が、データがされていないことを確認することができます、データのデジタル署名するメカニズムを提供、転送中に変更します。</span><span class="sxs-lookup"><span data-stu-id="58747-110">*Data integrity* provides mechanisms to digitally sign data, so that the receiver can ensure that the data has not been altered in-transit.</span></span>  
  
 <span data-ttu-id="58747-111">問題になるもう 1 つの重要な領域は、ユーザー名パスワード資格情報を提供する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="58747-111">Another important area of concern is the user-name password credentials that you supply to the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="58747-112">アダプターでは、これらの資格情報を使用して、SQL システムへの接続を開きます。</span><span class="sxs-lookup"><span data-stu-id="58747-112">The adapter uses these credentials to open connections to the SQL system.</span></span> <span data-ttu-id="58747-113">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続 URI で指定する資格情報ではできません。</span><span class="sxs-lookup"><span data-stu-id="58747-113">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not allow credentials to be supplied in the connection URI.</span></span> <span data-ttu-id="58747-114">これは、資格情報が誤って公開されるを取得することを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="58747-114">This prevents the credentials from getting exposed inadvertently.</span></span> <span data-ttu-id="58747-115">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]より安全な方法でこれらの資格情報を指定する 2 つの代替メソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="58747-115">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] provides two alternative methods to supply these credentials in a more secure manner:</span></span>  
  
 <span data-ttu-id="58747-116">統合セキュリティ。</span><span class="sxs-lookup"><span data-stu-id="58747-116">Integrated Security.</span></span> <span data-ttu-id="58747-117">ここで、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 、Microsoft を使用して[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]資格情報。</span><span class="sxs-lookup"><span data-stu-id="58747-117">In this case, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] uses the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] credentials.</span></span> <span data-ttu-id="58747-118">このメソッドを使用するこれらの資格情報を受け入れるように SQL server を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58747-118">You must configure the SQL server to accept these credentials for this method to work.</span></span>  
  
 <span data-ttu-id="58747-119">エンタープライズ シングル サインオン (SSO)。</span><span class="sxs-lookup"><span data-stu-id="58747-119">Enterprise Single Sign-on (SSO).</span></span> <span data-ttu-id="58747-120">詳細については、SSO を使用して、次を参照してください。 [SQL アダプターと BizTalk Server によるセキュリティ](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)です。</span><span class="sxs-lookup"><span data-stu-id="58747-120">For more information about using SSO, see [Security with the SQL adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md) .</span></span>  
  
 <span data-ttu-id="58747-121">このセクションのトピックでは、向上に役立つガイドラインで開発したソリューションのセキュリティを提供、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="58747-121">The topics in this section provide guidelines to help you better secure the solutions that you develop with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="58747-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="58747-122">In This Section</span></span>  
  
-   [<span data-ttu-id="58747-123">SQL Server とアダプター間のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="58747-123">Security between the SQL Server and the adapter</span></span>](../../adapters-and-accelerators/adapter-sql/security-between-the-sql-server-and-the-adapter.md)
  
-   [<span data-ttu-id="58747-124">SQL アダプタと BizTalk Server でのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="58747-124">Security with the SQL adapter and BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md) 
  
-   [<span data-ttu-id="58747-125">SQL アダプタをセキュリティで保護された使用したプログラミング</span><span class="sxs-lookup"><span data-stu-id="58747-125">Secure programming with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/secure-programming-with-the-sql-adapter.md)
  
-   [<span data-ttu-id="58747-126">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="58747-126">Best practices</span></span>](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)