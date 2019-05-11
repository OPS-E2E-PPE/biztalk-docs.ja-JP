---
title: 公開済み Web サービスをテストする .NET アプリケーションの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- testing, Web services
- Web services, testing
ms.assetid: 94b2223b-45d7-4b86-b4ec-87cc027d7e2a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 323ba7b5cce1d7cd83c9031f51ca7944ae5f5bb1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390126"
---
# <a name="creating-a-net-application-to-test-a-published-web-service"></a><span data-ttu-id="081d2-102">公開済み Web サービスをテストする .NET アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="081d2-102">Creating a .NET Application to Test a Published Web Service</span></span>
<span data-ttu-id="081d2-103">公開された Web サービスをテストするには、公開済み Web サービスを使用する ASP.NET Web クライアント アプリケーションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="081d2-103">To test your published Web service, you can create an ASP.NET Web client application that consumes your published Web service.</span></span> <span data-ttu-id="081d2-104">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ヘルプ コレクションには、ASP.NET Web クライアント アプリケーションを作成するため貴重なチュートリアルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="081d2-104">The [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help Collection contains a valuable walkthrough for creating an ASP.NET Web client application.</span></span> <span data-ttu-id="081d2-105">このチュートリアルを使用して、公開済み Web サービスをテストすることができます。</span><span class="sxs-lookup"><span data-stu-id="081d2-105">You can use the walkthrough to test your published Web service.</span></span>  
  
 <span data-ttu-id="081d2-106">チュートリアルでは、ASP.NET Web クライアント アプリケーションを作成し、Web 参照の場合を追加して、公開された Web サービスにアクセスする方法について説明するサンプル コードを提供します。</span><span class="sxs-lookup"><span data-stu-id="081d2-106">The walkthrough creates an ASP.NET Web client application, adds a Web reference, and provides sample code to show you how to access your published Web service.</span></span> <span data-ttu-id="081d2-107">このチュートリアルは、デバッグ モードでアプリケーションを実行します。</span><span class="sxs-lookup"><span data-stu-id="081d2-107">The walkthrough takes you through running the application in debug mode.</span></span>  
  
 <span data-ttu-id="081d2-108">情報および XML Web サービス クライアント プロジェクトを作成する方法の手順では、次を参照してください。"チュートリアル。Visual Basic または Visual を使用して XML Web サービスへのアクセスC#"で、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ヘルプ コレクション[ http://go.microsoft.com/fwlink/?LinkId=62263](http://go.microsoft.com/fwlink/?LinkId=62263)します。</span><span class="sxs-lookup"><span data-stu-id="081d2-108">For information and procedures about creating an XML Web service client project, see "Walkthrough: Accessing an XML Web Service Using Visual Basic or Visual C#" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help Collection at [http://go.microsoft.com/fwlink/?LinkId=62263](http://go.microsoft.com/fwlink/?LinkId=62263).</span></span> <span data-ttu-id="081d2-109">この例では、tempconvert1 というで使用する Web サービスを置き換えることができます、biztalk Web サービスを公開します。</span><span class="sxs-lookup"><span data-stu-id="081d2-109">You can replace the Web service used in this example, TempConvert1, with a BizTalk published Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="081d2-110">参照</span><span class="sxs-lookup"><span data-stu-id="081d2-110">See Also</span></span>  
 [<span data-ttu-id="081d2-111">公開済み Web サービスのテスト</span><span class="sxs-lookup"><span data-stu-id="081d2-111">Testing Published Web Services</span></span>](../core/testing-published-web-services.md)