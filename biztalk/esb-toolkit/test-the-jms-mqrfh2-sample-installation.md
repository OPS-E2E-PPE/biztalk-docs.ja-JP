---
title: "JMS MQRFH2 サンプルのインストールをテスト |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 965e985d-f0fe-4b0f-b01b-cf98d1e2f6a4
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5970f12479cddfb6a635cbd00dd139495a2f6242
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="test-the-jms-mqrfh2-sample-installation"></a><span data-ttu-id="60355-102">JMS MQRFH2 サンプルのインストールをテストします。</span><span class="sxs-lookup"><span data-stu-id="60355-102">Test the JMS MQRFH2 Sample Installation</span></span>
<span data-ttu-id="60355-103">インストールが成功したのと操作をチェックすることができます、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] JMS MQRFH2 サンプル サンプル シナリオのいずれかを実行する前にします。</span><span class="sxs-lookup"><span data-stu-id="60355-103">You can check for successful installation and operation of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] JMS MQRFH2 sample before you execute any of the sample scenarios.</span></span>  
  
 <span data-ttu-id="60355-104">**JMS MQRFH2 サンプルのインストールをテストするには**</span><span class="sxs-lookup"><span data-stu-id="60355-104">**To test the JMS MQRFH2 sample installation**</span></span>  
  
1.  <span data-ttu-id="60355-105">"RFHUtil"を使用して JMS \Source\Samples\JMS\Test\Data\Load フォルダーで ESB をという名前のキューにテスト メッセージを記述するユーティリティをテストします。JMS です。サンプルです。SENDTOBIZTALK です。</span><span class="sxs-lookup"><span data-stu-id="60355-105">Use the "RFHUtil" JMS test utility to write the test messages in the \Source\Samples\JMS\Test\Data\Load folder to the queue named ESB.JMS.SAMPLE.SENDTOBIZTALK.</span></span>  
  
2.  <span data-ttu-id="60355-106">このサンプルでは、送信先キューおよび、応答キューにメッセージのコピーに、メッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="60355-106">The sample sends the message to the destination queue and a copy of the message to the reply queue.</span></span>