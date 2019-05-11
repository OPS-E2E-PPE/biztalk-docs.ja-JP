---
title: リゾルバーとアダプターのプロバイダー フレームワークの拡張 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4d5e6f2-b3bc-46e2-b8f7-d7e271d4a8c0
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e53c9284ec85e86cbf3a79ca73d6a819049933f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400334"
---
# <a name="extending-the-resolver-and-adapter-provider-framework"></a>リゾルバーとアダプターのプロバイダー フレームワークの拡張
リゾルバーとアダプターのプロバイダー フレームワークは、エンドポイントと変換の解決とルーティングのサポートを提供し、サービスのカスタム メタデータも提供します。 フレームワークを動的にエンドポイントを解決および送信アダプターのプロパティを設定します。 競合回避モジュールの後にコンポーネント (たとえば、送信 URL を検索する Universal Description, Discovery, and Integration [UDDI] を使用して) エンドポイントの解決、アダプター プロバイダーのコンポーネントが登録されている Microsoft BizTalk Server アダプターの特定のプロパティを設定します。  
  
 これには、リゾルバーとアダプターのプロバイダー フレームワークを拡張する 3 つの主な領域があります。  
  
-   [カスタム リゾルバーを作成する](../esb-toolkit/creating-a-custom-resolver.md)  
  
-   [Unity コンテナーでカスタム リゾルバーを作成する](../esb-toolkit/creating-a-custom-resolver-with-a-unity-container.md)  
  
-   [カスタム アダプター プロバイダーを作成する](../esb-toolkit/creating-a-custom-adapter-provider.md)