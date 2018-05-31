---
title: ESB リゾルバーとアダプターのプロバイダー フレームワーク |Microsoft ドキュメント
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
ms.openlocfilehash: c23fa8aca6def654b594d8b4fccf5d584e12fed4
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/01/2017
ms.locfileid: "26007371"
---
# <a name="esb-resolver-and-adapter-provider-framework"></a>ESB リゾルバーとアダプターのプロバイダー フレームワーク
アダプター プロバイダーのフレームワークとの競合回避モジュールを動的にエンドポイント情報と BizTalk Server マップの種類を解決する包括的なプラグ可能なアーキテクチャを提供します。 開発者が独自の要件に合わせて、別の解決方法およびルーティング メソッドをサポートするためのメカニズムを拡張する動作を変更できるようにの拡張コンポーネントを使用します。  
  
 アダプター プロバイダーのフレームワークとの競合回避モジュールは、Universal Description, Discovery, と Integration (UDDI)、ビジネス ルール エンジン (BRE)、および XML Path Language (XPath) のサポートを提供します。 また、開発者のインターフェイスを公開 (**IResolveProvider**と**IAdapterProvider**) カスタム競合回避モジュール コンポーネントとアダプター コンポーネントの作成を許可します。 競合回避モジュールとアダプターのプロバイダー フレームワークの 3 つの主要なコンポーネントを次に示します。  
  
-   **競合回避モジュール。** これらは定義されていますがスキーマでは、接続文字列での実装を通して、 **IResolveProvider** .NET Framework アセンブリにおけるインターフェイスです。 実行時にキャッシュされ、解像度の種類と接続文字列の範囲をサポートこれらが読み込まれます。  
  
-   **アダプター プロバイダーです。** これらの実装によって定義されます、 **IAdapterProvider** .NET Framework アセンブリ内でのインターフェイスです。 これらは、BizTalk Server トランスポートの種類、これは、適切な BizTalk Server アダプターで競合回避モジュールによって提供されるエンドポイント情報を設定して登録されます。  
  
-   **Itinerary パイプライン コンポーネントです。** これらの接続文字列とは、ESB 行程 SOAP ヘッダーからの解決指示を解析して、解像度や変換の実行機能が、競合回避モジュールとアダプターのプロバイダー フレームワークを使用してエンドポイントを提供します。 コンポーネントが動的にエンドポイントのプロパティを BizTalk Server を設定または接続文字列とは、ESB 行程 SOAP ヘッダーからの解決指示に基づいて、BizTalk Server マップ変換を実行できます。 これらのコンポーネントは、管理、更新、およびプロセスやサービス境界を越えて、日程を永続化します。 省略可能な逆アセンブラー コンポーネントは、BizTalk Server メッセージと実装の解析をネイティブを提供、[!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]オーケストレーション サービスの必要としない複数のエンドポイントへのルーティングの機能です。  
  
 動的な解像度と動的ルーティングの詳細については、次を参照してください。[動的解決の使用とルーティング](../esb-toolkit/using-dynamic-resolution-and-routing.md)と[を使用して動的変換](../esb-toolkit/using-dynamic-transformation.md)です。 解像度とアダプターのプロバイダー フレームワークについては、次を参照してください。[変更および拡張 BizTalk ESB Toolkit](../esb-toolkit/modifying-and-extending-the-biztalk-esb-toolkit.md)です。