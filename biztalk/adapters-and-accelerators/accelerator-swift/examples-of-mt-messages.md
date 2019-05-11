---
title: MT メッセージの例 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 629042cc-b941-4c58-b0dd-ede056caf573
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d6406a5d1e11ddeefd0aeb86c0d350acf5892361
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378033"
---
# <a name="examples-of-mt-messages"></a><span data-ttu-id="c88fe-102">MT メッセージの例</span><span class="sxs-lookup"><span data-stu-id="c88fe-102">Examples of MT Messages</span></span>
<span data-ttu-id="c88fe-103">**異なる MT メッセージのソリューション (InfoPath フォーム テンプレート) を生成するためのコマンドします。**</span><span class="sxs-lookup"><span data-stu-id="c88fe-103">**Commands to generate the solution (InfoPath form template) for the Different MT messages:**</span></span>  
  
 <span data-ttu-id="c88fe-104">次の例では、"SWIFT ベース Types.xsd"、"SWIFT 共通データ Types.xsd","MT102.xsd"、"MT500.xsd"および"MT103.xsd"スキーマは c:\schemas すべてであることが必要です。</span><span class="sxs-lookup"><span data-stu-id="c88fe-104">The following examples require that the "SWIFT Base Types.xsd", "SWIFT Common Data Types.xsd","MT102.xsd", "MT500.xsd", and "MT103.xsd" schemas are all in c:\schemas.</span></span> <span data-ttu-id="c88fe-105">これにより、"C:\GeneratedForms"フォルダー内の InfoPath フォーム テンプレートのソリューションが生成されます。</span><span class="sxs-lookup"><span data-stu-id="c88fe-105">This will generate the solution for InfoPath Form Template in the "C:\GeneratedForms" folder.</span></span> <span data-ttu-id="c88fe-106">ソリューションのフォルダー名は、メッセージを生成する必要がある InfoPath フォームの名前と同じになります。</span><span class="sxs-lookup"><span data-stu-id="c88fe-106">The folder name of the solution would be same as the name of the message for which the InfoPath form needs to be generated.</span></span> <span data-ttu-id="c88fe-107">これらの例では、ユーティリティが"C:\FormGeneratorUtility2008"フォルダーに配置されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="c88fe-107">These examples assume that the utility has been placed in “C:\FormGeneratorUtility2008” folder.</span></span> <span data-ttu-id="c88fe-108">ユーティリティでの選択した場所を置き換える、以下のコマンド。</span><span class="sxs-lookup"><span data-stu-id="c88fe-108">Replace the location that you have selected for the utility in the below commands.</span></span>  
  
-   <span data-ttu-id="c88fe-109">**MT103 スキーマ用のフォームを生成するには。**</span><span class="sxs-lookup"><span data-stu-id="c88fe-109">**To generate a form for the MT103 schema:**</span></span>  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas MT103`  
  
-   <span data-ttu-id="c88fe-110">**MT103、MT102、および MT500 スキーマ用のフォームを生成するには。**</span><span class="sxs-lookup"><span data-stu-id="c88fe-110">**To generate a form for the MT103, MT102, and MT500 schema:**</span></span>  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas MT103 MT102 MT500`  
  
-   <span data-ttu-id="c88fe-111">**(ファイル) から MT103 スキーマ用のフォームを生成するには。**</span><span class="sxs-lookup"><span data-stu-id="c88fe-111">**To generate a form for the MT103 schema (from the file):**</span></span>  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas -f P1forms.txt`