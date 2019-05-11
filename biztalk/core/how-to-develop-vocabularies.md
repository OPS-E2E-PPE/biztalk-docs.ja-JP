---
title: ボキャブラリを作成する方法 |Microsoft Docs
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
ms.openlocfilehash: 1aac6d9350b3f93df3755b3b082db9e8e5ab7f6f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65338427"
---
# <a name="how-to-develop-vocabularies"></a>ボキャブラリを作成する方法
ルール条件およびアクションは、詳細な可能性があります、ユーザーのほとんど、またはを参照しているところを示す読み取り困難なバインド情報ソースに基づいています。 ビジネス ルール フレームワークでは、ユーザーは、ルール条件およびアクションに関連付けることが、直感的なドメイン固有の用語をユーザーに提供することで、ルールの開発を簡略化するボキャブラリを作成することができます。  
  
 使用して、新しいボキャブラリを作成するデータ ソースを特定し、ボキャブラリの定義を追加することができます。 ボキャブラリのバージョンを保存するにはルール ストアへとそれが完了したら、ユーザー データの参照にバインドされている用語の明確に定義された、変更できないセットを提供することを発行できます。  
  
 今後のボキャブラリを変更する必要がある場合だけ、変更を反映するボキャブラリの新しいバージョンを作成できます。  
  
> [!CAUTION]
>  ボキャブラリの新しいバージョンが作成されると、以前のバージョンから構築されている規則は引き続き 以前のバージョンを指します。  
  
### <a name="to-create-a-vocabulary"></a>ボキャブラリを作成するには  
  
1.  [ファクト エクスプ ローラー] ウィンドウ、**ボキャブラリ**タブ。  
  
2.  右クリックし、**ボキャブラリ**フォルダー、およびクリック**新しいボキャブラリの追加**します。  
  
     新しい**ボキャブラリ**下のフォルダーに表示されます、**ボキャブラリ**フォルダー。  
  
3.  [新規] をクリックして**ボキャブラリ**フォルダー、および [プロパティ] ウィンドウで名前を編集します。  
  
    > [!NOTE]
    >  ポリシーまたはボキャブラリの名前を変更する前に、すべてのもの (定義のすべてのバージョン) を保存する必要があります。