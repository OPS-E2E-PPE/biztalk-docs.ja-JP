---
title: "Oracle EBS アプリケーションのセキュリティ保護 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 76147120-57a8-4959-a0ff-77d04dee06a6
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a9a7427d36ead6ba91e0d68b1080c9ab4f5155fa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="secure-your-oracle-ebs-applications"></a><span data-ttu-id="febbf-102">Oracle EBS アプリケーションのセキュリティ保護します。</span><span class="sxs-lookup"><span data-stu-id="febbf-102">Secure your Oracle EBS applications</span></span>
<span data-ttu-id="febbf-103">Oracle E-business アプリケーションは、顧客のアカウント詳細などの機密性の高いビジネス情報を処理します。</span><span class="sxs-lookup"><span data-stu-id="febbf-103">Oracle E-Business applications deal with sensitive business information such as customer account details.</span></span> <span data-ttu-id="febbf-104">使用するアプリケーション、[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]にアクセスして、この情報を変更するいずれかのローカルまたは分散ネットワーク経由で公開される可能性が誤ってに不正のアクターによってアクセスする作業はに対して保護して、中にデータをセキュリティで保護しない限り、転送します。</span><span class="sxs-lookup"><span data-stu-id="febbf-104">Applications that use the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] to access and modify this information either locally or across a distributed network might inadvertently expose it to access by unauthorized actors, unless efforts are made to protect and secure the data during transmission.</span></span> <span data-ttu-id="febbf-105">データ保護およびセキュリティは、通常と考えるは次の用語で。</span><span class="sxs-lookup"><span data-stu-id="febbf-105">Data protection and security are usually thought of in the following terms:</span></span>  
  
-   <span data-ttu-id="febbf-106">*承認*要求者の身元に基づいて、リソースへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="febbf-106">*Authorization* controls access to a resource based on the identity of the requester.</span></span>  
  
-   <span data-ttu-id="febbf-107">*認証*要求者の身元を確認するためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="febbf-107">*Authentication* provides mechanisms for verifying the identity of a requester.</span></span>  
  
-   <span data-ttu-id="febbf-108">*データの機密性*暗号化によるデータのプライバシーを保護するためのメカニズムを提供します。</span><span class="sxs-lookup"><span data-stu-id="febbf-108">*Data confidentiality* provides mechanisms for protecting the privacy of data through encryption.</span></span>  
  
-   <span data-ttu-id="febbf-109">*データの整合性*受信側が、データがされていないことを確認することができます、データのデジタル署名するメカニズムを提供、転送中に変更します。</span><span class="sxs-lookup"><span data-stu-id="febbf-109">*Data integrity* provides mechanisms to digitally sign data, so that the receiver can ensure that the data has not been altered in-transit.</span></span>  
  
 <span data-ttu-id="febbf-110">問題になるもう 1 つの重要な領域は、ユーザー名パスワード資格情報を提供する、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="febbf-110">Another important area of concern is the user-name password credentials that you supply to the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="febbf-111">アダプターでは、これらの資格情報を使用して、Oracle データベースへの接続を開きます。</span><span class="sxs-lookup"><span data-stu-id="febbf-111">The adapter uses these credentials to open connections to the Oracle database.</span></span> <span data-ttu-id="febbf-112">これらの資格情報を指定する接続 URI です。ただし、ユーザー名とパスワードはクリア テキストであるため、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]より安全な方法でこれらの資格情報を指定するのに使用できる代替のメソッドを提供します。</span><span class="sxs-lookup"><span data-stu-id="febbf-112">These credentials can be supplied in the connection URI; however, because the user name and password are clear text, the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] provides alternative methods that you can use to supply these credentials in a more secure manner.</span></span>  
  
 <span data-ttu-id="febbf-113">このセクションのトピックでは、向上に役立つガイドラインで開発したソリューションのセキュリティを提供、[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]です。</span><span class="sxs-lookup"><span data-stu-id="febbf-113">The topics in this section provide guidelines to help you better secure the solutions that you develop with the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span>  
  
