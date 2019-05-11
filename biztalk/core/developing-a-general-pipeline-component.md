---
title: 全般パイプライン コンポーネントの開発 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63f5d8d1-30fb-4a1e-b4bd-2be07b618b20
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7debc394b29676b15f330a8b5c22fbfe4656d0a5
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65351542"
---
# <a name="developing-a-general-pipeline-component"></a>全般パイプライン コンポーネントの開発

## <a name="interfaces"></a>インターフェイス
全般パイプライン コンポーネントは、次のインターフェイスを実装する .NET または COM コンポーネントです。  
  
- IBaseComponent インターフェイス (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
- IComponent インターフェイス (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
- IComponentUI インターフェイス (COM) [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
- [IPersistPropertyBag](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.ole.interop.ipersistpropertybag)
  
  全般パイプライン コンポーネントの 1 つのメッセージを BizTalk メッセージング エンジンから取得、処理し、しを返します、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]エンジン。 メッセージをサーバーに返されないように全般コンポーネントを実装することもできます。 このようなコンポーネントでは、コンポーネントはメッセージを受信しますが、結果メッセージは生成されませんのでを破棄するコンポーネントと呼ばれます。  
  
> [!NOTE]
>  カスタム パイプライン コンポーネントは、出力メッセージ用に、入力メッセージからその他のパーツをコピーする必要があります。 これはさらに、パイプラインで処理するためを保持します。  
  
## <a name="more-pipeline-resources"></a>パイプラインの他のリソース
 [アセンブラー パイプライン コンポーネントの開発](../core/developing-an-assembling-pipeline-component.md)   
 [逆アセンブラー パイプライン コンポーネントの開発](../core/developing-a-disassembling-pipeline-component.md)   
 [プローブ パイプライン コンポーネントの開発](../core/developing-a-probing-pipeline-component.md)   
 [パイプライン コンポーネントからエラーの報告](../core/reporting-errors-from-pipeline-components.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)   
 [パイプライン コンポーネントの展開](../core/deploying-pipeline-components.md)   
 [CustomComponent (BizTalk Server サンプル)](../core/customcomponent-biztalk-server-sample.md)