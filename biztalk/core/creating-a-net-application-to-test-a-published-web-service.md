---
title: "公開された Web サービスをテストする .NET アプリケーションの作成 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- testing, Web services
- Web services, testing
ms.assetid: 94b2223b-45d7-4b86-b4ec-87cc027d7e2a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d13c69a471d546fe8d2b70363dad5cced8bbe62f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-net-application-to-test-a-published-web-service"></a><span data-ttu-id="a7223-102">公開された Web サービスをテストする .NET アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7223-102">Creating a .NET Application to Test a Published Web Service</span></span>
<span data-ttu-id="a7223-103">公開対象 Web サービスをテストするには、公開対象 Web サービスを使用する ASP.NET Web クライアント アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="a7223-103">To test your published Web service, you can create an ASP.NET Web client application that consumes your published Web service.</span></span> <span data-ttu-id="a7223-104">[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ヘルプ コレクションには、ASP.NET Web クライアント アプリケーションを作成するための有用なチュートリアルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="a7223-104">The [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help Collection contains a valuable walkthrough for creating an ASP.NET Web client application.</span></span> <span data-ttu-id="a7223-105">このチュートリアルを使用して、公開対象 Web サービスをテストできます。</span><span class="sxs-lookup"><span data-stu-id="a7223-105">You can use the walkthrough to test your published Web service.</span></span>  
  
 <span data-ttu-id="a7223-106">このチュートリアルでは、ASP.NET Web クライアント アプリケーションが作成され、Web 参照が追加されるほか、公開対象 Web サービスにアクセスする方法を示すサンプル コードが提供されます。</span><span class="sxs-lookup"><span data-stu-id="a7223-106">The walkthrough creates an ASP.NET Web client application, adds a Web reference, and provides sample code to show you how to access your published Web service.</span></span> <span data-ttu-id="a7223-107">アプリケーションの実行は、デバッグ モードで行われます。</span><span class="sxs-lookup"><span data-stu-id="a7223-107">The walkthrough takes you through running the application in debug mode.</span></span>  
  
 <span data-ttu-id="a7223-108">XML Web サービス クライアント プロジェクトの作成に関する情報および手順を参照してください「チュートリアル: へのアクセス、XML Web サービスを使用して Visual Basic または Visual c#」で、[!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]ヘルプ コレクション[http://go.microsoft.com/fwlink/?LinkId=62263](http://go.microsoft.com/fwlink/?LinkId=62263)です。</span><span class="sxs-lookup"><span data-stu-id="a7223-108">For information and procedures about creating an XML Web service client project, see "Walkthrough: Accessing an XML Web Service Using Visual Basic or Visual C#" in the [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] Help Collection at [http://go.microsoft.com/fwlink/?LinkId=62263](http://go.microsoft.com/fwlink/?LinkId=62263).</span></span> <span data-ttu-id="a7223-109">この例で使用される、TempConvert1 という Web サービスは、BizTalk で公開する Web サービスで置換できます。</span><span class="sxs-lookup"><span data-stu-id="a7223-109">You can replace the Web service used in this example, TempConvert1, with a BizTalk published Web service.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7223-110">参照</span><span class="sxs-lookup"><span data-stu-id="a7223-110">See Also</span></span>  
 [<span data-ttu-id="a7223-111">公開済み Web サービスのテスト</span><span class="sxs-lookup"><span data-stu-id="a7223-111">Testing Published Web Services</span></span>](../core/testing-published-web-services.md)