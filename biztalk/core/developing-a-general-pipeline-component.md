---
title: 全般パイプライン コンポーネントの開発 |Microsoft ドキュメント
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
ms.openlocfilehash: 44b85992eb0691b7f27ec1a52812d986429d9e31
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239218"
---
# <a name="developing-a-general-pipeline-component"></a>全般パイプライン コンポーネントの開発

## <a name="interfaces"></a>インターフェイス
全般パイプライン コンポーネントは、次のインターフェイスを実装する .NET コンポーネントまたは COM コンポーネントです。  
  
-   IBaseComponent インターフェイス (COM)[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
-   IComponent インターフェイス (COM)[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
-   IComponentUI インターフェイス (COM)[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]
  
-   [IPersistPropertyBag](https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.ole.interop.ipersistpropertybag)
  
 全般パイプライン コンポーネントは、BizTalk メッセージング エンジンからメッセージを 1 つ取得して処理し、そのメッセージを [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] エンジンに返します。 メッセージがサーバーに返されないように全般コンポーネントを実装することもできます。 このようなコンポーネントは、メッセージを受信しても結果メッセージをまったく生成しないので、"メッセージを破棄するコンポーネント" と呼ばれます。  
  
> [!NOTE]
>  カスタム パイプライン コンポーネントでは入力メッセージの追加部分を出力メッセージにコピーする必要があります。 これにより、パイプラインでの後続の処理のために追加部分が保持されます。  
  
## <a name="more-pipeline-resources"></a>パイプラインの他のリソース
 [アセンブラー パイプライン コンポーネントの開発](../core/developing-an-assembling-pipeline-component.md)   
 [逆アセンブラー パイプライン コンポーネントの開発](../core/developing-a-disassembling-pipeline-component.md)   
 [プローブ パイプライン コンポーネントの開発](../core/developing-a-probing-pipeline-component.md)   
 [パイプライン コンポーネントからエラーの報告](../core/reporting-errors-from-pipeline-components.md)   
 [ネイティブ パイプライン コンポーネントの構成](../core/configuring-native-pipeline-components.md)   
 [パイプライン コンポーネントの展開](../core/deploying-pipeline-components.md)   
 [CustomComponent (BizTalk Server サンプル)](../core/customcomponent-biztalk-server-sample.md)