---
title: "ThrowDetailedError スイッチを使用する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Web services, security
- Web services, debugging
ms.assetid: 8a8af3c0-a9a2-42fe-b0be-a5a106403747
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 194306da3b021e7460b88a3d8e76801a2eeaebba
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-the-throwdetailederror-switch"></a><span data-ttu-id="8e098-102">ThrowDetailedError スイッチを使用する方法</span><span class="sxs-lookup"><span data-stu-id="8e098-102">How to Use the ThrowDetailedError Switch</span></span>
<span data-ttu-id="8e098-103">Web クライアントがジェネリック型を受け取るエラーが発生する場合**SoapException**です。</span><span class="sxs-lookup"><span data-stu-id="8e098-103">If an error occurs, the Web client receives a generic **SoapException**.</span></span>  
  
 <span data-ttu-id="8e098-104">公開された Web サービスをデバッグするには、この Web サービスから返される例外の詳細レベルを制御するためのスイッチを Web.config ファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="8e098-104">To debug your published Web service, you can add a switch to the Web.config file to control the level of the exception details returned from the published Web service.</span></span>  
  
 <span data-ttu-id="8e098-105">Web.config ファイルを含む、アプリケーション設定スイッチ**ThrowDetailedError**です。</span><span class="sxs-lookup"><span data-stu-id="8e098-105">The Web.config file contains an application setting switch, **ThrowDetailedError**.</span></span> <span data-ttu-id="8e098-106">**False**の既定の設定は、 **ThrowDetailedError**です。</span><span class="sxs-lookup"><span data-stu-id="8e098-106">**False** is the default setting for **ThrowDetailedError**.</span></span> <span data-ttu-id="8e098-107">設定を変更する場合**True**、サーバー プロキシは、公開された Web サービスをデバッグできるように、Web クライアントには、内部例外情報を返します。</span><span class="sxs-lookup"><span data-stu-id="8e098-107">If you change the setting to **True**, the server proxy returns inner exception information to the Web client enabling you to debug the published Web service.</span></span>  
  
 <span data-ttu-id="8e098-108">次の XML コードは、 **ThrowDetailedError**スイッチ下にある Web.config ファイルに表示される、 \<appSettings > ノード。</span><span class="sxs-lookup"><span data-stu-id="8e098-108">The following XML code shows the **ThrowDetailedError** switch that appears in the Web.config file under the \<appSettings> node:</span></span>  
  
```  
<appSettings>  
  <add key="ThrowDetailedError" value="False" />  
<appSettings/>  
```  
  
> [!IMPORTANT]
>  <span data-ttu-id="8e098-109">内部例外情報には、アプリケーション呼び出し履歴などの機密性の高い情報が含まれている場合があります。そのため、BizTalk Server は、内部例外情報を Web クライアントに返しません。</span><span class="sxs-lookup"><span data-stu-id="8e098-109">BizTalk Server does not return inner exception information to the Web client by default since it may contain sensitive information, such as application call stacks.</span></span> <span data-ttu-id="8e098-110">設定する必要があります、デバッグ後に、 **ThrowDetailedError**設定**False**です。</span><span class="sxs-lookup"><span data-stu-id="8e098-110">After debugging, you should set the **ThrowDetailedError** setting to **False**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e098-111">参照</span><span class="sxs-lookup"><span data-stu-id="8e098-111">See Also</span></span>  
 [<span data-ttu-id="8e098-112">公開済み Web サービスのデバッグ</span><span class="sxs-lookup"><span data-stu-id="8e098-112">Debugging Published Web Services</span></span>](../core/debugging-published-web-services.md)