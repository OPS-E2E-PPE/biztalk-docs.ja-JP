---
title: Oracle データベース アプリケーションのセキュリティ保護 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- adapter, security
- authorization
- data protection
- adapter, data protection
- authentication
- security
ms.assetid: c5f18b0a-1c8e-44c6-ba7e-470fa186f636
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e7f61e15b94d741e6bfc2a9f951655ff4358a001
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36982915"
---
# <a name="secure-your-oracle-database-applications"></a><span data-ttu-id="c196b-102">Oracle データベース アプリケーションのセキュリティ保護します。</span><span class="sxs-lookup"><span data-stu-id="c196b-102">Secure your Oracle Database applications</span></span>
## <a name="data-protection-and-security-overview"></a><span data-ttu-id="c196b-103">データの保護とセキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="c196b-103">Data protection and security overview</span></span>
<span data-ttu-id="c196b-104">多くの場合、データベースには、顧客アカウントの詳細などの機密性の高いビジネス情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c196b-104">A database often contains sensitive business information such as customer account details.</span></span> <span data-ttu-id="c196b-105">使用するアプリケーション、[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]にアクセスして、この情報を変更するいずれかまたは分散ネットワーク経由でローカルにキーが誤って公開、不正なアクターによってアクセス中にデータをセキュリティで保護する取り組みが行われた場合を除き、転送します。</span><span class="sxs-lookup"><span data-stu-id="c196b-105">Applications that use the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] to access and modify this information either locally or across a distributed network might inadvertently expose it to access by unauthorized actors, unless efforts are made to protect and secure the data during transmission.</span></span> <span data-ttu-id="c196b-106">データ保護とセキュリティは、通常と考えられるので、次の用語。</span><span class="sxs-lookup"><span data-stu-id="c196b-106">Data protection and security are usually thought of in the following terms:</span></span>  
  
- <span data-ttu-id="c196b-107">*承認*要求者の id に基づいてリソースへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="c196b-107">*Authorization* controls access to a resource based on the identity of the requester.</span></span>  
  
- <span data-ttu-id="c196b-108">*認証*要求者の id を検証するためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="c196b-108">*Authentication* provides mechanisms for verifying the identity of a requester.</span></span>  
  
- <span data-ttu-id="c196b-109">*データの機密性*暗号化を通じてデータのプライバシーを保護するためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="c196b-109">*Data confidentiality* provides mechanisms for protecting the privacy of data through encryption.</span></span>  
  
- <span data-ttu-id="c196b-110">*データの整合性*データのデジタル署名するためのメカニズムを提供、受信側が、データの有効期限がされていないことを確認することができます、転送中に変更します。</span><span class="sxs-lookup"><span data-stu-id="c196b-110">*Data integrity* provides mechanisms to digitally sign data, so that the receiver can ensure that the data has not been altered in-transit.</span></span>  
  
  <span data-ttu-id="c196b-111">問題のもう 1 つの重要な領域は、ユーザー名パスワード資格情報に指定する、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c196b-111">Another important area of concern is the user-name password credentials that you supply to the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="c196b-112">アダプターでは、これらの資格情報を使用して、Oracle データベースへの接続を開きます。</span><span class="sxs-lookup"><span data-stu-id="c196b-112">The adapter uses these credentials to open connections to the Oracle database.</span></span> <span data-ttu-id="c196b-113">これらの資格情報を指定する接続 URI。ただし、ユーザー名とパスワードはクリア テキストであるため、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]より安全な方法でこれらの資格情報を指定するために使用できる代替のメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="c196b-113">These credentials can be supplied in the connection URI; however, because the user name and password are clear text, the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)] provides alternative methods that you can use to supply these credentials in a more secure manner.</span></span>  
  
  <span data-ttu-id="c196b-114">このセクションのトピックで説明に役立つガイドラインで開発したソリューションをセキュリティで保護された、[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]します。</span><span class="sxs-lookup"><span data-stu-id="c196b-114">The topics in this section provide guidelines to help you better secure the solutions that you develop with the [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c196b-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c196b-115">In this section</span></span>  
  
-   [<span data-ttu-id="c196b-116">Oracle データベースとアダプター間のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="c196b-116">Security between the Oracle Database and the adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/security-between-the-oracle-database-and-the-adapter.md)
  
-   [<span data-ttu-id="c196b-117">Oracle データベース アダプターと BizTalk Server でのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="c196b-117">Security with the Oracle Database adapter and BizTalk Server</span></span>](../../adapters-and-accelerators/adapter-oracle-database/security-with-the-oracle-database-adapter-and-biztalk-server.md)  
  
-   [<span data-ttu-id="c196b-118">Oracle データベース アダプターを使用したプログラミングをセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="c196b-118">Secure programming with the Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/secure-programming-with-the-oracle-database-adapter.md) 
  
-   [<span data-ttu-id="c196b-119">ベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="c196b-119">Best practices</span></span>](../../adapters-and-accelerators/adapter-oracle-database/best-practices-to-secure-the-oracle-database-adapter.md)