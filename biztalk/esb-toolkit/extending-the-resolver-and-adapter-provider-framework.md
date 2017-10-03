---
title: "競合回避モジュールとアダプターのプロバイダー フレームワークの拡張 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b4d5e6f2-b3bc-46e2-b8f7-d7e271d4a8c0
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b6ab5caf03d113e313e00a74c11641058e86b886
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="extending-the-resolver-and-adapter-provider-framework"></a>競合回避モジュールとアダプターのプロバイダー フレームワークの拡張
アダプター プロバイダーのフレームワークとの競合回避モジュールは、エンドポイントと変換の解像度と、ルーティングのサポートを提供し、サービスのカスタム メタデータも提供します。 フレームワークを動的にエンドポイントを解決および送信アダプターのプロパティを設定します。 競合回避モジュールの後にコンポーネント (たとえば、送信 URL を検索する Universal Description, Discovery, and Integration [UDDI] を使用して) エンドポイントを解決する、アダプター プロバイダーのコンポーネントが登録されている Microsoft BizTalk Server アダプターの特定のプロパティを設定します。  
  
 これには、競合回避モジュールとアダプターのプロバイダー フレームワークを拡張する 3 つの主な領域があります。  
  
-   [カスタム競合回避モジュールを作成します。](../esb-toolkit/creating-a-custom-resolver.md)  
  
-   [Unity コンテナーとカスタム競合回避モジュールを作成します。](../esb-toolkit/creating-a-custom-resolver-with-a-unity-container.md)  
  
-   [カスタム アダプター プロバイダーの作成](../esb-toolkit/creating-a-custom-adapter-provider.md)