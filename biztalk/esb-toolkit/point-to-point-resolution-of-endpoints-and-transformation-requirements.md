---
title: ポイント ツー ポイントの解像度のエンドポイントと変換の要件 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c4c570bf-8274-4779-ae83-2aef2bf57ded
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8899c5f713f1c9ebfe299d3e431754dd8b9794d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22294466"
---
# <a name="point-to-point-resolution-of-endpoints-and-transformation-requirements"></a>エンドポイントおよび変換の要件のポイント間の解決
このユース ケースでは、Web サービス クライアントは、ESB を通らずに Web サービスを呼び出します。 2 つのポイントが直接、通信が、Web サービスのエンドポイントを解決する必要があります、クライアントは、呼び出しを行い、前にします。 Web サービスへの呼び出しは、一方向または要求-応答のいずれかにできます。 これを実現するための 1 つの方法では、図 1 に示すように、ESB の動的な解決機能を使用します。  
  
 ![ポイント &#45; へ (& a) #45 です。エンドポイントのポイント解決](../esb-toolkit/media/ch3-pointtopoint.gif "Ch3 ポイントツー ポイント ・")  
  
 **図 1**  
  
 **UDDI を使用してエンドポイントを解決します。**  
  
 含まれているリゾルバー サービスのサンプル、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示しています。 サンプルは、Universal Description, Discovery, and Integration (UDDI)、XML パス言語 (XPath) など、バックエンド ストアの内容を開発しているように、解決をテストすることにより解決を実行する ESB リゾルバー サービスを呼び出す方法を示しています。スタティック、または BizTalk Server のビジネス ルール エンジンのポリシー。  
  
 詳細については、次を参照してください。[をインストールすると、リゾルバー サービスのサンプルを実行している](../esb-toolkit/installing-and-running-the-resolver-service-sample.md)です。