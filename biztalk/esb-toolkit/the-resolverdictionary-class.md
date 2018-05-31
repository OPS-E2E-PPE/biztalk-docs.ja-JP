---
title: ResolverDictionary クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 46deb8a0-0523-4a5c-ac6b-45c506de7a72
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a2dfe0082ffc7f7b68c5c56811a28d5ccd20e93e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22295002"
---
# <a name="the-resolverdictionary-class"></a>ResolverDictionary クラス
**ResolverDictionary**クラスは、**ディクショナリ**-クラスのインスタンスに格納できる、**リゾルバー**としてクラス**文字列**名前/値のペア。 インスタンスを作成するときに、 **ResolverDictionary**クラス、既存の参照を提供する必要があります**ディクショナリ**インスタンス。 **ResolverDictionary**クラスのデータを提供する、**リゾルバー**クラスの実行時の解像度の実行時に使用します。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]インストーラーがインストールおよび登録され、 **Microsoft.Practices.ESB.Resolver.dll**を持つアセンブリ、 **ResolverDictionary**グローバル アセンブリ キャッシュ内のクラスです。  
  
 **ResolverDictionary**クラスは、1 つのメソッドと 1 つのプロパティを公開します。  
  
-   **項目 (** キー **)** です。 このメソッドは、キー名を表す文字列値を受け取ります。 基になるアイテムが存在しない場合、対応する文字列値または空の文字列を返します、**ディクショナリ**インスタンス。  
  
-   **BaseDictionary**です。 このプロパティは、基になるへの参照を返します**ディクショナリ**インスタンス。