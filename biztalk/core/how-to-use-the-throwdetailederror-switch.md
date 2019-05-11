---
title: ThrowDetailedError スイッチを使用する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Web services, security
- Web services, debugging
ms.assetid: 8a8af3c0-a9a2-42fe-b0be-a5a106403747
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 160bf585d23ad366d04e9b897c66d45ef8be6bda
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65333189"
---
# <a name="how-to-use-the-throwdetailederror-switch"></a><span data-ttu-id="4dfb1-102">ThrowDetailedError スイッチを使用する方法</span><span class="sxs-lookup"><span data-stu-id="4dfb1-102">How to Use the ThrowDetailedError Switch</span></span>
<span data-ttu-id="4dfb1-103">Web クライアントが受け取るジェネリックでエラーが発生する場合**SoapException**します。</span><span class="sxs-lookup"><span data-stu-id="4dfb1-103">If an error occurs, the Web client receives a generic **SoapException**.</span></span>  
  
 <span data-ttu-id="4dfb1-104">公開済み Web サービスをデバッグするには、公開された Web サービスから返された例外の詳細のレベルを制御するために Web.config ファイルにスイッチを追加できます。</span><span class="sxs-lookup"><span data-stu-id="4dfb1-104">To debug your published Web service, you can add a switch to the Web.config file to control the level of the exception details returned from the published Web service.</span></span>  
  
 <span data-ttu-id="4dfb1-105">Web.config ファイルには、アプリケーション設定スイッチが含まれています**ThrowDetailedError**します。</span><span class="sxs-lookup"><span data-stu-id="4dfb1-105">The Web.config file contains an application setting switch, **ThrowDetailedError**.</span></span> <span data-ttu-id="4dfb1-106">**False**の既定の設定は、 **ThrowDetailedError**します。</span><span class="sxs-lookup"><span data-stu-id="4dfb1-106">**False** is the default setting for **ThrowDetailedError**.</span></span> <span data-ttu-id="4dfb1-107">設定を変更する場合**True**、サーバー プロキシは、公開された Web サービスをデバッグできるように、Web クライアントに内部例外情報を返します。</span><span class="sxs-lookup"><span data-stu-id="4dfb1-107">If you change the setting to **True**, the server proxy returns inner exception information to the Web client enabling you to debug the published Web service.</span></span>  
  
 <span data-ttu-id="4dfb1-108">次の XML コードは、 **ThrowDetailedError**スイッチで Web.config ファイルに表示される、 \<appSettings\>ノード。</span><span class="sxs-lookup"><span data-stu-id="4dfb1-108">The following XML code shows the **ThrowDetailedError** switch that appears in the Web.config file under the \<appSettings\> node:</span></span>  
  
```  
<appSettings>  
  <add key="ThrowDetailedError" value="False" />  
<appSettings/>  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="4dfb1-109">BizTalk Server 情報は返されません、内部例外を Web クライアントに既定ではアプリケーションのコール スタックなどの機密情報が含まれている可能性がありますので。</span><span class="sxs-lookup"><span data-stu-id="4dfb1-109">BizTalk Server does not return inner exception information to the Web client by default since it may contain sensitive information, such as application call stacks.</span></span> <span data-ttu-id="4dfb1-110">デバッグするには、後に設定する必要があります、 **ThrowDetailedError**設定**False**します。</span><span class="sxs-lookup"><span data-stu-id="4dfb1-110">After debugging, you should set the **ThrowDetailedError** setting to **False**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4dfb1-111">参照</span><span class="sxs-lookup"><span data-stu-id="4dfb1-111">See Also</span></span>  
 [<span data-ttu-id="4dfb1-112">公開済み Web サービスのデバッグ</span><span class="sxs-lookup"><span data-stu-id="4dfb1-112">Debugging Published Web Services</span></span>](../core/debugging-published-web-services.md)