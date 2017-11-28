---
title: "MT メッセージの例を示します |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 629042cc-b941-4c58-b0dd-ede056caf573
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 73098c20aeb03e8013f7e20e04c8bb37ce31266e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="examples-of-mt-messages"></a><span data-ttu-id="42647-102">MT メッセージの例</span><span class="sxs-lookup"><span data-stu-id="42647-102">Examples of MT Messages</span></span>
<span data-ttu-id="42647-103">**ソリューション (InfoPath フォーム テンプレート) を異なる MT メッセージを生成するためのコマンドします。**</span><span class="sxs-lookup"><span data-stu-id="42647-103">**Commands to generate the solution (InfoPath form template) for the Different MT messages:**</span></span>  
  
 <span data-ttu-id="42647-104">次の例では、"SWIFT ベース Types.xsd"、"SWIFT 共通データ Types.xsd","MT102.xsd"、"MT500.xsd"および"MT103.xsd"のスキーマをすべて c:\schemas が必要です。</span><span class="sxs-lookup"><span data-stu-id="42647-104">The following examples require that the "SWIFT Base Types.xsd", "SWIFT Common Data Types.xsd","MT102.xsd", "MT500.xsd", and "MT103.xsd" schemas are all in c:\schemas.</span></span> <span data-ttu-id="42647-105">これにより、"C:\GeneratedForms"フォルダー内の InfoPath フォーム テンプレートのソリューションが生成されます。</span><span class="sxs-lookup"><span data-stu-id="42647-105">This will generate the solution for InfoPath Form Template in the "C:\GeneratedForms" folder.</span></span> <span data-ttu-id="42647-106">ソリューションのフォルダー名は、メッセージを生成する必要がある InfoPath フォームの名前と同じになります。</span><span class="sxs-lookup"><span data-stu-id="42647-106">The folder name of the solution would be same as the name of the message for which the InfoPath form needs to be generated.</span></span> <span data-ttu-id="42647-107">これらの例では、ユーティリティが"C:\FormGeneratorUtility2008"フォルダーに格納されていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="42647-107">These examples assume that the utility has been placed in “C:\FormGeneratorUtility2008” folder.</span></span> <span data-ttu-id="42647-108">ユーティリティ用に選択した場所を交換して、以下のコマンド。</span><span class="sxs-lookup"><span data-stu-id="42647-108">Replace the location that you have selected for the utility in the below commands.</span></span>  
  
-   <span data-ttu-id="42647-109">**MT103 スキーマ用にフォームを生成します。**</span><span class="sxs-lookup"><span data-stu-id="42647-109">**To generate a form for the MT103 schema:**</span></span>  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas MT103`  
  
-   <span data-ttu-id="42647-110">**MT103、MT102、および MT500 スキーマ用にフォームを生成します。**</span><span class="sxs-lookup"><span data-stu-id="42647-110">**To generate a form for the MT103, MT102, and MT500 schema:**</span></span>  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas MT103 MT102 MT500`  
  
-   <span data-ttu-id="42647-111">**(ファイル) から MT103 スキーマ用にフォームを生成するには。**</span><span class="sxs-lookup"><span data-stu-id="42647-111">**To generate a form for the MT103 schema (from the file):**</span></span>  
  
     `FormGenerator.exe -b “C:\FormGeneratorUtility2008\TemplateDS\InfoPath Form Template" c:\generatedforms c:\schemas -f P1forms.txt`