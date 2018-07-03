---
title: プライベート プロセス チュートリアル |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- private processes, tutorial
- private process tutorial
- tutorials, private process tutorial
ms.assetid: 58affc48-af73-406e-895f-696bc284d945
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7e598690b2249352a7e89341be8fa90110cd8c0f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36981619"
---
# <a name="private-process-tutorial"></a>プライベート プロセス チュートリアル
このチュートリアルには、Microsoft® を使用して完全なエンド ツー エンド ソリューションが含まれています。[!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]します。 ここでは、RosettaNet 準拠のソリューションを実装するために従う必要のある手順について詳しく説明します。この手順では、Contoso 社 (サプライヤー組織) と Fabrikam 社 (購入者組織) という 2 つの架空の会社間の取引シナリオを作成します。  
  
 このチュートリアルが実装するシナリオでは、3A2 - Price and Availability PIP (Partner Interface Process) を使用します。 購入の前に、購入者である Fabrikam が 3A2 - Price and Availability Request をサプライヤーである Contoso に送信します。 この PIP により、Fabrikam は製品に関する情報を取得し、その情報をビジネス ルールによって処理して、製品を購入するかどうかを決定することができます。 次の図は、3A2 PIP の交換時における開始側の組織と応答側の組織の通信パターンを示しています。  
  
 ![&#60;変更なし&#62;](../../adapters-and-accelerators/accelerator-rosettanet/media/rn3-intro-eetut-3a2flow.gif "RN3_Intro_EETut_3A2Flow")  
  
 このチュートリアルでは、Contoso ソリューションに焦点を当てています。 ここでは、ERP の統合、ビジネス ポリシーの実施、プライベート プロセスのカスタマイズ、およびセキュリティで保護された通信の使用など、RosettaNet ベースのソリューションの作成についてさまざまな角度から概説しています。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [プライベート プロセス チュートリアルの準備](../../adapters-and-accelerators/accelerator-rosettanet/preparing-for-the-private-process-tutorial.md)  
  
-   [Contoso ソリューションの作成](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-contoso-solution.md)  
  
-   [Fabrikam ソリューションの作成](../../adapters-and-accelerators/accelerator-rosettanet/creating-the-fabrikam-solution.md)  
  
-   [ソリューションのテスト](../../adapters-and-accelerators/accelerator-rosettanet/testing-the-solution.md)