---
title: スキーマ プロジェクトの作成 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 67e6278c-a597-4700-80bf-48e37aaa9c05
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a6419c008a95277256c75fbd0b7d6dda388061f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65378457"
---
# <a name="creating-a-schema-project"></a><span data-ttu-id="9218a-102">スキーマ プロジェクトの作成</span><span class="sxs-lookup"><span data-stu-id="9218a-102">Creating a Schema Project</span></span>
<span data-ttu-id="9218a-103">スキーマ プロジェクトを作成するには</span><span class="sxs-lookup"><span data-stu-id="9218a-103">To create a schema project:</span></span>  
  
1.  <span data-ttu-id="9218a-104">Visual Studio では、SWIFT MX スキーマの BizTalk プロジェクトを作成します。</span><span class="sxs-lookup"><span data-stu-id="9218a-104">In Visual Studio, create the SWIFT MX Schema BizTalk project.</span></span>  
  
2.  <span data-ttu-id="9218a-105">このプロジェクトに適切な MX スキーマ (ISO20022 サイトからダウンロード) をテストするには、これを追加します。</span><span class="sxs-lookup"><span data-stu-id="9218a-105">Add the appropriate MX schema (downloaded from ISO20022 site), which you wish to test, to this project.</span></span>  
  
3.  <span data-ttu-id="9218a-106">上記のメッセージの種類に対応するエンベロープ スキーマを展開する必要がありますし、上記の MX メッセージの Message Repair and New Submission の機能を実行する場合は、それ以外の場合手順 6 に進みます。</span><span class="sxs-lookup"><span data-stu-id="9218a-106">If you want to execute the Message Repair and New Submission functionality for the above MX message, then an Envelope schema corresponding to the above message type also needs to be deployed else proceed to step 6.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9218a-107">MX エンベロープ スキーマを生成する方法については、フォーム ジェネレーターのマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9218a-107">For information on how to generate MX Envelope schemas, please refer to the Form Generator Documentation.</span></span>  
  
4.  <span data-ttu-id="9218a-108">エンベロープ スキーマは、SWIFT MX スキーマ プロジェクトに追加します。</span><span class="sxs-lookup"><span data-stu-id="9218a-108">Add the Envelope schema to the SWIFT MX Schema project.</span></span>  
  
5.  <span data-ttu-id="9218a-109">BizTalk エディターで、エンベロープ スキーマを開き、"CorrelationToken"と"IsNewSubmission"プロパティを昇格します。</span><span class="sxs-lookup"><span data-stu-id="9218a-109">Open the Envelope schema in the BizTalk editor and promote “CorrelationToken” and “IsNewSubmission” properties.</span></span> <span data-ttu-id="9218a-110">上記のフィールドを右クリックし、をクリックして**昇格クイック昇格]-> [** にこれらのプロパティを昇格します。</span><span class="sxs-lookup"><span data-stu-id="9218a-110">Right-click the above fields and click **Promote -> Quick Promotion** to promote these properties.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9218a-111">スキーマのプロパティを昇格させる方法の詳細については、BizTalk Server のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9218a-111">For more information on how to promote properties of a schema, please refer to the BizTalk Server documentation.</span></span>  
  
6.  <span data-ttu-id="9218a-112">(Sn – k key.snk を使用して) キー ファイルを作成し、強力なを作成するプロジェクトに割り当てます、という名前のアセンブリ。</span><span class="sxs-lookup"><span data-stu-id="9218a-112">Create a key file (using Sn –k key.snk), and then assign it to the project to create a strong named assembly.</span></span>  
  
7.  <span data-ttu-id="9218a-113">ビルドし、プロジェクトを配置します。</span><span class="sxs-lookup"><span data-stu-id="9218a-113">Build and then deploy the project.</span></span>