---
title: デザイナー機能拡張サンプルのしくみ |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8f4dc622-28b8-498d-961f-df969cff9dcb
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 963c5ae2f778f193135fa73366d81cc359f5a798
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397118"
---
# <a name="how-the-designer-extensibility-sample-works"></a>デザイナー機能拡張サンプルのしくみ
デザイナーの機能拡張サンプル内の各プロジェクトに 2 つのクラスが含まれています。**エクステンダー**クラスおよび**拡張機能プロバイダー**クラス。 これらのクラスが、機能を拡張し、のプロパティを定義するように設計、 **ItineraryDsl**モデル要素。  
  
 **拡張機能プロバイダー**クラスから派生、 **ExtensionProviderBase**クラスし、いる、 **ExtensionProviderAttribute**プロパティとそれらに適用します。拡張機能とその目的を特定します。 ユーザーが設定されるときにそのこれらの値が、デザイナーでユーザーに表示される、**エクステンダー**モデル要素のプロパティ。 ときに、**拡張機能プロバイダー**のコンス トラクターを呼び出すクラスの初期化、 **ExtensionProviderBase**エクステンダー クラスの型を渡すとします。  
  
 **エクステンダー**クラスが、 **ObjectExtender** ; に適用される属性、 **ObjectExtender**内のオブジェクトの型を渡される、属性、 **ItineraryDsl**拡張するものです。 これらのクラスの基本クラスは、エクステンダーの種類によって異なります。 基本クラスは、競合回避モジュールのエクステンダーの**ObjectExtender\<リゾルバー\>** します。 基本クラスは、旅行プラン サービスのエクステンダーの**ItineraryServiceExtenderBase**します。 **エクステンダー**クラスでは、次の属性がプロパティに適用されます属性プロパティ グリッドで適切に表示するために必要な検証のために、Microsoft Enterprise Library に含まれる属性。適切なシリアル化に必要な属性やプロパティを永続化する方法を決定する属性。  
  
 これらのアセンブリがコンパイルされ、Lib フォルダーに配置の読み込み時と実行時に、デザイナーによってキャッシュされます。 エクステンダーは、必要に応じて、 **ItineraryDsl**リフレクションを使用してキャッシュからエクスポートされた型とそれらの型の属性を調べることで適用可能なアセンブリを読み込みます。