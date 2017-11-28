---
title: "スキーマ プロジェクトを作成する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 67e6278c-a597-4700-80bf-48e37aaa9c05
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 58017b24f7b7464745f48cc202734217dfb327d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="creating-a-schema-project"></a><span data-ttu-id="c2b9a-102">スキーマ プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c2b9a-102">Creating a Schema Project</span></span>
<span data-ttu-id="c2b9a-103">スキーマのプロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="c2b9a-103">To create a schema project:</span></span>  
  
1.  <span data-ttu-id="c2b9a-104">Visual Studio では、SWIFT MX スキーマの BizTalk プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="c2b9a-104">In Visual Studio, create the SWIFT MX Schema BizTalk project.</span></span>  
  
2.  <span data-ttu-id="c2b9a-105">適切な MX (ISO20022 サイトからダウンロード) をスキーマにテストするには、このプロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="c2b9a-105">Add the appropriate MX schema (downloaded from ISO20022 site), which you wish to test, to this project.</span></span>  
  
3.  <span data-ttu-id="c2b9a-106">上記のメッセージの種類に対応するエンベロープ スキーマを展開する必要がありますし、上記の MX メッセージの Message Repair and New Submission の機能を実行する場合は、それ以外の場合手順 6. に進みます。</span><span class="sxs-lookup"><span data-stu-id="c2b9a-106">If you want to execute the Message Repair and New Submission functionality for the above MX message, then an Envelope schema corresponding to the above message type also needs to be deployed else proceed to step 6.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c2b9a-107">MX エンベロープ スキーマを生成する方法については、フォーム ジェネレーターは、ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2b9a-107">For information on how to generate MX Envelope schemas, please refer to the Form Generator Documentation.</span></span>  
  
4.  <span data-ttu-id="c2b9a-108">SWIFT MX スキーマ プロジェクトには、エンベロープ スキーマを追加します。</span><span class="sxs-lookup"><span data-stu-id="c2b9a-108">Add the Envelope schema to the SWIFT MX Schema project.</span></span>  
  
5.  <span data-ttu-id="c2b9a-109">BizTalk エディターで、エンベロープ スキーマを開き、"CorrelationToken"および"IsNewSubmission"プロパティを昇格します。</span><span class="sxs-lookup"><span data-stu-id="c2b9a-109">Open the Envelope schema in the BizTalk editor and promote “CorrelationToken” and “IsNewSubmission” properties.</span></span> <span data-ttu-id="c2b9a-110">上記のフィールドを右クリックし、をクリックして**昇格クイック昇格]-> [**をこれらのプロパティを昇格させます。</span><span class="sxs-lookup"><span data-stu-id="c2b9a-110">Right-click the above fields and click **Promote -> Quick Promotion** to promote these properties.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c2b9a-111">スキーマのプロパティを昇格する方法の詳細については、BizTalk Server のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c2b9a-111">For more information on how to promote properties of a schema, please refer to the BizTalk Server documentation.</span></span>  
  
6.  <span data-ttu-id="c2b9a-112">(Sn – k key.snk を使用)、キー ファイルを作成し、強力なを作成するプロジェクトに割り当てます、名前のアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="c2b9a-112">Create a key file (using Sn –k key.snk), and then assign it to the project to create a strong named assembly.</span></span>  
  
7.  <span data-ttu-id="c2b9a-113">プロジェクトをビルドし、展開します。</span><span class="sxs-lookup"><span data-stu-id="c2b9a-113">Build and then deploy the project.</span></span>