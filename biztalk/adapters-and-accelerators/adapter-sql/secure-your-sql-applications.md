---
title: SQL アプリケーションのセキュリティ保護 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4b182593-fcca-4ebc-a2fd-7684b84cfb15
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: eabb9c260ed835a7c4cac3183000327767bb9cd0
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37014515"
---
# <a name="secure-your-sql-applications"></a><span data-ttu-id="69f72-102">SQL アプリケーションのセキュリティ保護します。</span><span class="sxs-lookup"><span data-stu-id="69f72-102">Secure your SQL applications</span></span>
## <a name="overview"></a><span data-ttu-id="69f72-103">概要</span><span class="sxs-lookup"><span data-stu-id="69f72-103">Overview</span></span>
<span data-ttu-id="69f72-104">SQL Server データベースは、多くの場合、顧客アカウントの詳細などの機密性の高いビジネス情報を含めます。</span><span class="sxs-lookup"><span data-stu-id="69f72-104">SQL Server databases often contain sensitive business information such as customer account details.</span></span> <span data-ttu-id="69f72-105">使用するアプリケーション、[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]にアクセスして、この情報を変更するいずれかまたは分散ネットワーク経由でローカルにキーが誤って公開、不正なアクターによってアクセス中にデータをセキュリティで保護する取り組みが行われた場合を除き、転送します。</span><span class="sxs-lookup"><span data-stu-id="69f72-105">Applications that use the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] to access and modify this information either locally or across a distributed network might inadvertently expose it to access by unauthorized actors, unless efforts are made to protect and secure the data during transmission.</span></span> <span data-ttu-id="69f72-106">データ保護とセキュリティは、通常と考えられるので、次の用語。</span><span class="sxs-lookup"><span data-stu-id="69f72-106">Data protection and security are usually thought of in the following terms:</span></span>  
  
- <span data-ttu-id="69f72-107">*承認*要求元の id に基づいてリソースへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="69f72-107">*Authorization* controls access to a resource based on the identity of the requestor.</span></span>  
  
- <span data-ttu-id="69f72-108">*認証*要求者の id を検証するためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="69f72-108">*Authentication* provides mechanisms for verifying the identity of a requestor.</span></span>  
  
- <span data-ttu-id="69f72-109">*データの機密性*暗号化を通じてデータのプライバシーを保護するためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="69f72-109">*Data confidentiality* provides mechanisms for protecting the privacy of data through encryption.</span></span>  
  
- <span data-ttu-id="69f72-110">*データの整合性*データのデジタル署名するためのメカニズムを提供、受信側が、データの有効期限がされていないことを確認することができます、転送中に変更します。</span><span class="sxs-lookup"><span data-stu-id="69f72-110">*Data integrity* provides mechanisms to digitally sign data, so that the receiver can ensure that the data has not been altered in-transit.</span></span>  
  
  <span data-ttu-id="69f72-111">問題のもう 1 つの重要な領域は、ユーザー名パスワード資格情報に指定する、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="69f72-111">Another important area of concern is the user-name password credentials that you supply to the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="69f72-112">アダプターでは、これらの資格情報を使用して、SQL システムへの接続を開きます。</span><span class="sxs-lookup"><span data-stu-id="69f72-112">The adapter uses these credentials to open connections to the SQL system.</span></span> <span data-ttu-id="69f72-113">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]接続 URI で指定する資格情報ではできません。</span><span class="sxs-lookup"><span data-stu-id="69f72-113">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] does not allow credentials to be supplied in the connection URI.</span></span> <span data-ttu-id="69f72-114">これは、資格情報が誤って公開されるを取得することを防ぎます。</span><span class="sxs-lookup"><span data-stu-id="69f72-114">This prevents the credentials from getting exposed inadvertently.</span></span> <span data-ttu-id="69f72-115">[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]より安全な方法でこれらの資格情報を提供する 2 つのメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="69f72-115">The [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] provides two alternative methods to supply these credentials in a more secure manner:</span></span>  
  
  <span data-ttu-id="69f72-116">統合セキュリティ。</span><span class="sxs-lookup"><span data-stu-id="69f72-116">Integrated Security.</span></span> <span data-ttu-id="69f72-117">ここで、 [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] 、Microsoft を使用して[!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)]資格情報。</span><span class="sxs-lookup"><span data-stu-id="69f72-117">In this case, the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)] uses the Microsoft [!INCLUDE[adapterpacknoversion](../../includes/adapterpacknoversion-md.md)] credentials.</span></span> <span data-ttu-id="69f72-118">このメソッドを使用するこれらの資格情報を受け入れるように SQL server を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69f72-118">You must configure the SQL server to accept these credentials for this method to work.</span></span>  
  
  <span data-ttu-id="69f72-119">エンタープライズ シングル サインオン (SSO)。</span><span class="sxs-lookup"><span data-stu-id="69f72-119">Enterprise Single Sign-on (SSO).</span></span> <span data-ttu-id="69f72-120">詳細については、SSO を使用して、[SQL アダプターと BizTalk Server でセキュリティ](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69f72-120">For more information about using SSO, see [Security with the SQL adapter and BizTalk Server](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md) .</span></span>  
  
  <span data-ttu-id="69f72-121">このセクションのトピックで説明に役立つガイドラインで開発したソリューションをセキュリティで保護された、[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="69f72-121">The topics in this section provide guidelines to help you better secure the solutions that you develop with the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="69f72-122">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="69f72-122">In This Section</span></span>  
  
-   [<span data-ttu-id="69f72-123">SQL Server とアダプターの間のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="69f72-123">Security between the SQL Server and the adapter</span></span>](../../adapters-and-accelerators/adapter-sql/security-between-the-sql-server-and-the-adapter.md)
  
-   [<span data-ttu-id="69f72-124">SQL アダプターと BizTalk Server でのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="69f72-124">Security with the SQL adapter and BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-sql/security-with-the-sql-adapter-and-biztalk-server.md) 
  
-   [<span data-ttu-id="69f72-125">SQL アダプターでの安全なプログラミング</span><span class="sxs-lookup"><span data-stu-id="69f72-125">Secure programming with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/secure-programming-with-the-sql-adapter.md)
  
-   [<span data-ttu-id="69f72-126">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="69f72-126">Best practices</span></span>](../../adapters-and-accelerators/adapter-sql/best-practices-to-secure-the-sql-adapter.md)