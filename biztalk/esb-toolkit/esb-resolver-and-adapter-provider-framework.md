---
title: ESB リゾルバーとアダプターのプロバイダー フレームワーク |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c82c2247-1f0a-48bd-98c2-9c816f4d68d7
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 900897c4b740f39dbec2f5f513b5e814d1589bf9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987027"
---
# <a name="esb-resolver-and-adapter-provider-framework"></a>ESB リゾルバーとアダプターのプロバイダー フレームワーク
リゾルバーとアダプターのプロバイダー フレームワークは、エンドポイント情報と BizTalk Server マップの型を動的に解決するため、プラグ可能な包括的なアーキテクチャを提供します。 開発者が、独自の要件に合うよう、別の解決とルーティング メソッドをサポートするためのメカニズムを拡張する動作を変更できるように、拡張可能なコンポーネントを使用します。  
  
 リゾルバーとアダプターのプロバイダー フレームワークは、Universal Description, Discovery, と Integration (UDDI)、ビジネス ルール エンジン (BRE)、および XML Path Language (XPath) のサポートを提供します。 また、開発者のインターフェイスを公開 (**IResolveProvider**と**IAdapterProvider**) リゾルバーとアダプターのカスタム コンポーネントの作成を許可します。 以下は、リゾルバーとアダプターのプロバイダー フレームワークの 3 つの主要なコンポーネントです。  
  
- **競合回避モジュール。** これら接続文字列の場合は、スキーマによって定義され、定義の実装によって、 **IResolveProvider** .NET Framework アセンブリでインターフェイス。 実行時にキャッシュされているし、さまざまな解像度の種類と接続文字列をサポートこれらが読み込まれます。  
  
- **アダプター プロバイダーです。** これらの実装によって定義されます、 **IAdapterProvider** .NET Framework アセンブリ内でのインターフェイス。 これらは、BizTalk Server トランスポートの種類、適切な BizTalk Server アダプターで競合回避モジュールによって提供されるエンドポイントの情報を設定して登録されます。  
  
- **スケジュール オンランプ パイプライン コンポーネント。** 解決手順については、ESB 行程 SOAP ヘッダーから、または接続文字列から解析これらと解像度や変換の実行機能がリゾルバーとアダプターのプロバイダー フレームワークを使用してエンドポイントを提供します。 コンポーネントが動的に BizTalk Server エンドポイントのプロパティを設定または ESB 行程 SOAP ヘッダーから、または接続文字列からの解決指示に基づいて、BizTalk Server マップ変換を実行できます。 これらのコンポーネントは、管理、更新、およびプロセスとサービスの境界を越えて、旅行プランを保持する責任を負います。 省略可能な逆アセンブラー コンポーネントは、BizTalk Server メッセージと実装の解析をネイティブ、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]オーケストレーション サービスを必要としない複数のエンドポイントへのルーティングの機能です。  
  
  動的解決と動的ルーティングの詳細については、次を参照してください。[を使用して動的な解決とルーティング](../esb-toolkit/using-dynamic-resolution-and-routing.md)と[を使用して動的変換](../esb-toolkit/using-dynamic-transformation.md)します。 解像度とアダプターのプロバイダー フレームワークについては、次を参照してください。[を変更すると、BizTalk ESB Toolkit の拡張](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)します。