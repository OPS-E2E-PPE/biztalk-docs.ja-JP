---
title: エンドポイントと変換の要件のポイント間の解決 |Microsoft Docs
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
ms.openlocfilehash: 518604865f05019b9f466efaf9b73f767143d247
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400033"
---
# <a name="point-to-point-resolution-of-endpoints-and-transformation-requirements"></a>エンドポイントと変換の要件のポイント間の解決
このユース ケースでは、Web サービス クライアントは、ESB を経由せずに Web サービスを呼び出します。 2 つの点は、直接通信が、Web サービスのエンドポイントを解決する必要があります、クライアントが呼び出しを行う前にします。 Web サービスへの呼び出しは、一方向または要求-応答のいずれかにできます。 これを実現するための 1 つの方法では、図 1 に示すように、ESB の動的な解決機能を使用します。  
  
 ![ポイント&#45;に&#45;エンドポイント解決ポイント](../esb-toolkit/media/ch3-pointtopoint.gif "Ch3-ポイントツー ポイント ・")  
  
 **図 1**  
  
 **UDDI を使用してエンドポイントを解決します。**  
  
 リゾルバー サービス サンプルに含まれている、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]このユース ケースを示します。 サンプルは、Universal Description, Discovery, and Integration (UDDI)、XML Path Language (XPath) など、バックエンド ストアの内容を開発しているように、解決をテストすることができます、解決を実行する ESB リゾルバー サービスを呼び出す方法を示しています。静的、または BizTalk Server ビジネス ルール エンジン ポリシー。  
  
 詳細については、次を参照してください。[をインストールすると、リゾルバー サービス サンプルを実行している](../esb-toolkit/installing-and-running-the-resolver-service-sample.md)します。