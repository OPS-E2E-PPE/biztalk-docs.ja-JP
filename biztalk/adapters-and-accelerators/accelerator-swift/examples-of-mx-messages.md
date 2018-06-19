---
title: MX メッセージの例を示します |Microsoft ドキュメント
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
ms.openlocfilehash: 7f5280f8ec2ce16344562907a95c1b0afa8c6627
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22209146"
---
# <a name="examples-of-mx-messages"></a><span data-ttu-id="44cb7-102">MX メッセージの例</span><span class="sxs-lookup"><span data-stu-id="44cb7-102">Examples of MX Messages</span></span>
<span data-ttu-id="44cb7-103">ソリューション (InfoPath フォーム テンプレート) を異なる MX メッセージを生成するコマンドライン</span><span class="sxs-lookup"><span data-stu-id="44cb7-103">Command Lines to generate the solution (InfoPath form template) for the Different MX messages</span></span>  
  
 <span data-ttu-id="44cb7-104">次の例では、"pacs.004.001.01"および"pain.002.001.01"のスキーマをすべて c:\schemas が必要です。</span><span class="sxs-lookup"><span data-stu-id="44cb7-104">The following examples require that the “pacs.004.001.01" and “pain.002.001.01” schemas are all in c:\schemas.</span></span> <span data-ttu-id="44cb7-105">これにより、"C:\GeneratedForms"フォルダー内の InfoPath フォーム テンプレートのソリューションが生成されます。</span><span class="sxs-lookup"><span data-stu-id="44cb7-105">This will generate the solution for InfoPath Form Template in the "C:\GeneratedForms" folder.</span></span> <span data-ttu-id="44cb7-106">ソリューションのフォルダー名は、メッセージを生成する必要がある InfoPath フォームの名前と同じになります。</span><span class="sxs-lookup"><span data-stu-id="44cb7-106">The folder name of the solution would be same as the name of the message for which the InfoPath form needs to be generated.</span></span> <span data-ttu-id="44cb7-107">これらの例では、ユーティリティが"C:\Program files \microsoft BizTalk Accelerator 用 SWIFT\SDK\FormGeneratorUtility"フォルダーに格納されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="44cb7-107">These examples assume that the utility has been placed in “C:\Program Files\Microsoft BizTalk Accelerator for SWIFT\SDK\FormGeneratorUtility” folder.</span></span> <span data-ttu-id="44cb7-108">ユーティリティ用に選択した場所を交換して、以下のコマンド。</span><span class="sxs-lookup"><span data-stu-id="44cb7-108">Replace the location that you have selected for the utility in the below commands.</span></span>  
  
-   <span data-ttu-id="44cb7-109">**Pacs.004.001.01 スキーマ用にフォームを生成します。**</span><span class="sxs-lookup"><span data-stu-id="44cb7-109">**To generate a form for the pacs.004.001.01 schema:**</span></span>  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\MXTemplates” " C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas pacs.004.001.01`  
  
-   <span data-ttu-id="44cb7-110">**Pacs.004.001.01 と pain.002.001.01 スキーマ用にフォームを生成するには。**</span><span class="sxs-lookup"><span data-stu-id="44cb7-110">**To generate a form for the pacs.004.001.01 and pain.002.001.01 schema:**</span></span>  
  
     `FormGenerator.exe -b -2 “C:\FormGeneratorUtility2008\MXTemplates” “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas pacs.004.001.01 pain.002.001.01`