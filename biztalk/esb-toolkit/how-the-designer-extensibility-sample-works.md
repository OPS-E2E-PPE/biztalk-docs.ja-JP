---
title: "デザイナーの機能拡張のサンプルの動作 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f4dc622-28b8-498d-961f-df969cff9dcb
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f78e5ab2c8a274b53b3cc580b37842772924af94
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2017
---
# <a name="how-the-designer-extensibility-sample-works"></a>デザイナーの機能拡張のサンプルのしくみ
デザイナーの機能拡張のサンプルでは、各プロジェクトには、2 つのクラスが含まれています。 **Extender**クラスおよび**拡張プロバイダー**クラスです。 これらのクラスが、機能を拡張しのプロパティを定義するように設計、 **ItineraryDsl**モデル要素。  
  
 **拡張プロバイダー**クラスから派生し、 **ExtensionProviderBase**クラスし、いる、 **ExtensionProviderAttribute**プロパティを持つそれらに適用します。拡張機能とその目的を識別します。 これらの値が表示されます、デザイナー内のユーザーにユーザーを設定するときに、 **Extender**モデル要素のプロパティです。 ときに、**拡張プロバイダー**のコンス トラクターを呼び出すクラスの初期化、 **ExtensionProviderBase** extender クラスの型を渡す。  
  
 **Extender**クラスがある、 **ObjectExtender**属性はそれらへの適用、 **ObjectExtender**内のオブジェクトの種類を通過するとき、属性、 **ItineraryDsl**拡張します。 これらのクラスの基底クラスは、extender の種類によって異なります。 基本クラスは、競合回避モジュールのエクステンダーの**ObjectExtender\<リゾルバー\>**です。 基本クラスは、行程サービス エクステンダーの**ItineraryServiceExtenderBase**です。 **Extender**クラス、次の属性は、プロパティに適用されます属性、プロパティ グリッドで適切な表示に必要な検証のために、Microsoft Enterprise Library に含まれる属性。適切なシリアル化に必要な属性やプロパティを永続化する方法を決定する属性。  
  
 これらのアセンブリでは、コンパイルされ、Lib フォルダーに配置することが、ときに、読み込まれ、デザイナーによって実行時にキャッシュします。 Extender は、必要に応じて、 **ItineraryDsl**アセンブリを読み込む、適用可能なキャッシュからエクスポートされた型とそれらの型の属性を調べることでリフレクションを使用します。