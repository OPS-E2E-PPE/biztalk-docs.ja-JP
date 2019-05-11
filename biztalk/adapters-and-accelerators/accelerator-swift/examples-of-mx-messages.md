---
title: MX メッセージの例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b592034f-2dd3-40e4-8f0b-eb6d65c38fff
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 26d86af52d8f93986d7028977166df8cfb28045c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65377893"
---
# <a name="examples-of-mx-messages"></a><span data-ttu-id="0b829-102">MX メッセージの例</span><span class="sxs-lookup"><span data-stu-id="0b829-102">Examples of MX Messages</span></span>
<span data-ttu-id="0b829-103">異なる MX メッセージのソリューション (InfoPath フォーム テンプレート) を生成するコマンドライン</span><span class="sxs-lookup"><span data-stu-id="0b829-103">Command Lines to generate the solution (InfoPath form template) for the Different MX messages</span></span>  
  
 <span data-ttu-id="0b829-104">次の例では、"pacs.004.001.01"と"pain.002.001.01"スキーマは c:\schemas すべてであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="0b829-104">The following examples require that the “pacs.004.001.01" and “pain.002.001.01” schemas are all in c:\schemas.</span></span> <span data-ttu-id="0b829-105">これにより、"C:\GeneratedForms"フォルダー内の InfoPath フォーム テンプレートのソリューションが生成されます。</span><span class="sxs-lookup"><span data-stu-id="0b829-105">This will generate the solution for InfoPath Form Template in the "C:\GeneratedForms" folder.</span></span> <span data-ttu-id="0b829-106">ソリューションのフォルダー名は、メッセージを生成する必要がある InfoPath フォームの名前と同じになります。</span><span class="sxs-lookup"><span data-stu-id="0b829-106">The folder name of the solution would be same as the name of the message for which the InfoPath form needs to be generated.</span></span> <span data-ttu-id="0b829-107">これらの例では、ユーティリティが"C:\Program files \microsoft BizTalk Accelerator 用 SWIFT\SDK\FormGeneratorUtility"フォルダーに配置されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="0b829-107">These examples assume that the utility has been placed in “C:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\FormGeneratorUtility” folder.</span></span> <span data-ttu-id="0b829-108">ユーティリティでの選択した場所を置き換える、以下のコマンド。</span><span class="sxs-lookup"><span data-stu-id="0b829-108">Replace the location that you have selected for the utility in the below commands.</span></span>  
  
-   <span data-ttu-id="0b829-109">**Pacs.004.001.01 スキーマ用のフォームを生成するには。**</span><span class="sxs-lookup"><span data-stu-id="0b829-109">**To generate a form for the pacs.004.001.01 schema:**</span></span>  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\MXTemplates” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas pacs.004.001.01`  
  
-   <span data-ttu-id="0b829-110">**Pacs.004.001.01 と pain.002.001.01 スキーマ用のフォームを生成するには。**</span><span class="sxs-lookup"><span data-stu-id="0b829-110">**To generate a form for the pacs.004.001.01 and pain.002.001.01 schema:**</span></span>  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\MXTemplates” “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas pacs.004.001.01 pain.002.001.01`