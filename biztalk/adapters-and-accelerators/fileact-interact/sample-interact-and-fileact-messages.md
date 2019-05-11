---
title: サンプルを操作および FileAct メッセージ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8552167c-2acc-4eae-a86a-55ba2e54d4a2
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 776659a7bcd6c882a514098758385123e4cfc0ea
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65366516"
---
# <a name="sample-interact-and-fileact-messages"></a><span data-ttu-id="4b79b-102">サンプルを操作および FileAct メッセージ</span><span class="sxs-lookup"><span data-stu-id="4b79b-102">Sample InterAct and FileAct Messages</span></span>
<span data-ttu-id="4b79b-103">InterAct および FileAct のリアルタイム メッセージのサンプルは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4b79b-103">Samples of InterAct and FileAct real-time messages are given below.</span></span>  
  
 <span data-ttu-id="4b79b-104">**InterAct のリアルタイム メッセージをサンプルします。**</span><span class="sxs-lookup"><span data-stu-id="4b79b-104">**Sample InterAct real-time message**</span></span>  
  
```  
<SwInt-ExchangeRequest>  
<SwInt-Request>  
<SwInt-RequestPayload>  
TestPayloadRequestSnF  
</SwInt-RequestPayload>  
</SwInt-Request>  
</SwInt-ExchangeRequest>  
```  
  
 <span data-ttu-id="4b79b-105">**サンプル FileAct のリアルタイム メッセージ (put 要求)**</span><span class="sxs-lookup"><span data-stu-id="4b79b-105">**Sample FileAct real-time message (put request)**</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<Sw-ExchangeFileRequest>  
<Sw-FileRequest>  
<Sw-FileOpRequest>  
<Sw-PutFileRequest>  
<Sw-PhysicalName>%PhysicalFolderName%\sample_put.txt</Sw-PhysicalName>  
</Sw-PutFileRequest>  
</Sw-FileOpRequest>  
</Sw-FileRequest>  
</Sw-ExchangeFileRequest>  
```  
  
 <span data-ttu-id="4b79b-106">**サンプル FileAct のリアルタイム メッセージ (get 要求)**</span><span class="sxs-lookup"><span data-stu-id="4b79b-106">**Sample FileAct real-time message (get request)**</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<Sw-ExchangeFileRequest>  
<Sw-FileRequest>  
<Sw-FileOpRequest>  
<Sw-GetFileRequest>  
<Sw-PhysicalName>%PhysicalFolderName%\sample_get.txt</Sw-PhysicalName>  
</Sw-GetFileRequest>  
</Sw-FileOpRequest>  
</Sw-FileRequest>  
</Sw-ExchangeFileRequest>  
```  
  
