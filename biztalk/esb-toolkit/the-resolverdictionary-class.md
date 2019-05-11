---
title: ResolverDictionary クラス |Microsoft Docs
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
ms.openlocfilehash: c1ec9080b0ad12910cc46a2844836a3b48887967
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399690"
---
# <a name="the-resolverdictionary-class"></a>ResolverDictionary クラス
**ResolverDictionary**クラスは、**ディクショナリ**-ベースのクラスのインスタンスを格納できる、**リゾルバー**クラスとして**文字列**名前/値のペア。 インスタンスを作成するときに、 **ResolverDictionary**クラスを既存の参照を提供する必要があります**ディクショナリ**インスタンス。 **ResolverDictionary**クラスの提供、データ、**リゾルバー**実行時の解決を実行するとき、クラスで使用します。  
  
 [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)]インストーラーがインストールおよび登録され、 **Microsoft.Practices.ESB.Resolver.dll**を持つアセンブリ、 **ResolverDictionary**グローバル アセンブリ キャッシュ内のクラス。  
  
 **ResolverDictionary**クラスが 1 つのメソッドと 1 つのプロパティを公開します。  
  
-   **項目 (** キー **)** します。 このメソッドは、キー名を表す文字列値を受け取ります。 基になるは、項目が存在しない場合、対応する文字列値または空の文字列を返します**ディクショナリ**インスタンス。  
  
-   **BaseDictionary**します。 このプロパティは、基になるへの参照を返します**ディクショナリ**インスタンス。