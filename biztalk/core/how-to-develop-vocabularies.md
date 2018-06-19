---
title: ボキャブラリを作成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- creating, vocabularies
- vocabularies, business rules
- business rules, vocabularies
- vocabularies, creating
ms.assetid: 5c16eb98-2257-44f2-8a29-899e02f7e556
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2644cc938cbe5e42f4e124453d863741755d965d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249058"
---
# <a name="how-to-develop-vocabularies"></a>ボキャブラリを作成する方法
ルールの条件とアクションには、送信元に基づくバインド情報が使用されるため、このバインド情報が何を指しているのか、ユーザーにわかるよう明確に定義されていることが大切です。 ビジネス ルール フレームワークでは、ボキャブラリを作成することによって、ユーザーがルールの条件とアクションを明確に理解できるような直観的かつドメイン固有の用語を定義し、ルールの開発プロセスを効率化できます。  
  
 使用するデータ ソースを明確に区別できるほか、新しいボキャブラリを作成したり、そこにボキャブラリ定義を追加することもできます。 ボキャブラリのバージョンをルール ストアに保存しておき、準備が整った段階で、それを公開することによって、ユーザーはデータと用語との関連性を確実に把握できるようになります。  
  
 将来ボキャブラリに修正が必要となった場合は、変更内容を反映した新しいボキャブラリ バージョンを作成するだけで済みます。  
  
> [!CAUTION]
>  新しいボキャブラリ バージョンを作成しても、既存のボキャブラリを基に作成されたルールは、依然として古いほうのバージョンを参照します。  
  
### <a name="to-create-a-vocabulary"></a>新しいボキャブラリを作成するには  
  
1.  [ファクト エクスプ ローラー] ウィンドウ、**ボキャブラリ**タブです。  
  
2.  右クリックし、**ボキャブラリ**フォルダー、およびクリック**新しいボキャブラリの追加**です。  
  
     新しい**ボキャブラリ**下のフォルダーに表示されます、**ボキャブラリ**フォルダーです。  
  
3.  クリックして、新しい**ボキャブラリ**フォルダー、および [プロパティ] ウィンドウ内の名前を編集します。  
  
    > [!NOTE]
    >  ボキャブラリまたはポリシーの名前を変更するには、すべてのバージョンの定義が保存されている必要があります。