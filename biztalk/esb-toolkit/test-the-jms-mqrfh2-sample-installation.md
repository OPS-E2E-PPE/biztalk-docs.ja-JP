---
title: JMS MQRFH2 サンプル インストールのテスト |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 965e985d-f0fe-4b0f-b01b-cf98d1e2f6a4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d22f609ef8de65845ff36cc1e60b2942faa956de
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65268670"
---
# <a name="test-the-jms-mqrfh2-sample-installation"></a><span data-ttu-id="5b416-102">JMS MQRFH2 サンプル インストールをテストします。</span><span class="sxs-lookup"><span data-stu-id="5b416-102">Test the JMS MQRFH2 Sample Installation</span></span>
<span data-ttu-id="5b416-103">正常にインストールしの操作を確認できます、 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] JMS MQRFH2 サンプル サンプル シナリオのいずれかを実行する前にします。</span><span class="sxs-lookup"><span data-stu-id="5b416-103">You can check for successful installation and operation of the [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] JMS MQRFH2 sample before you execute any of the sample scenarios.</span></span>  
  
 <span data-ttu-id="5b416-104">**JMS MQRFH2 サンプル インストールをテストするには**</span><span class="sxs-lookup"><span data-stu-id="5b416-104">**To test the JMS MQRFH2 sample installation**</span></span>  
  
1.  <span data-ttu-id="5b416-105">"RFHUtil"を使用して、JMS \Source\Samples\JMS\Test\Data\Load フォルダーで ESB という名前のキューにテスト メッセージを記述するためのユーティリティをテストします。JMS します。サンプルです。SENDTOBIZTALK します。</span><span class="sxs-lookup"><span data-stu-id="5b416-105">Use the "RFHUtil" JMS test utility to write the test messages in the \Source\Samples\JMS\Test\Data\Load folder to the queue named ESB.JMS.SAMPLE.SENDTOBIZTALK.</span></span>  
  
2.  <span data-ttu-id="5b416-106">このサンプルでは、送信先キューを返信キューにメッセージのコピーをメッセージを送信します。</span><span class="sxs-lookup"><span data-stu-id="5b416-106">The sample sends the message to the destination queue and a copy of the message to the reply queue.</span></span>