---
title: ポリシー エクスプ ローラーを使用して |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, Policy Explorer
- policies, Policy Explorer
- business rules, Policy Explorer
- Policy Explorer [Business Rule Composer]
ms.assetid: 249b1b72-ba84-4695-ba2b-16f081710b20
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 77c1366f47b16f48fdd362a83e5b63219a352933
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65396567"
---
# <a name="using-policy-explorer"></a>ポリシー エクスプ ローラーを使用します。
ポリシー エクスプ ローラーを使用して、ルール ストアにおけるポリシーとルールを管理することができます。 作成、変更、およびポリシーとルールを削除し、テスト、公開、展開、およびポリシーを展開解除します。  
  
 次の表では、新しいポリシーとルールの開発中で使用できるポリシー エクスプ ローラー内のコマンドについて説明します。  
  
|プロパティ|目的|  
|--------------|----------------|  
|**新しいポリシーを追加します。**|新しいポリシー (ルール セット) を作成します。|  
|**新しいバージョンを追加します。**|選択したポリシーの新しい空のバージョンを作成します。 他のバージョンからルールをコピーし、新しいバージョンに貼り付けることできます。|  
|**コピー (ポリシーのバージョン)**|選択したポリシーのバージョンをクリップボードにコピーします。|  
|**コピー (ルール)**|選択したルールをクリップボードにコピーします。|  
|**切り取り (ルール)**|選択したルールをクリップボードにコピーして削除します。|  
|**貼り付け (ポリシーのバージョン)**|選択したポリシーには、ポリシーのバージョンとその内容を貼り付けます。|  
|**貼り付け (ルール)**|選択したポリシーのバージョンには、ルールを貼り付けます。|  
|**削除 (ポリシーのバージョン)**|選択したポリシーのバージョンを削除します。|  
|**削除 (ルール)**|選択したルールを削除します。|  
|**削除**|選択したポリシーとすべてのバージョンを削除します。|  
|**新しい規則を追加します。**|選択したポリシーのバージョンの新しいルールを作成します。|  
|**および**|選択したバージョンとそのルールに加えられた変更を保存します。|  
|**発行**|選択したポリシーのバージョンを発行します。 公開されたバージョンを直接変更できないことに注意してください。 コピーして、ポリシーの新しいバージョンに貼り付けます。|  
|**再読み込み**|選択したポリシーのバージョンとそのバージョンで現在の変更を破棄するオプションを使用してそのルールでは、再読み込みし、ルール ストアからその内容を復元します。|  
|**配置**|公開済みのポリシー バージョンをデプロイします。 ルール ベースのアプリケーションで使用できるようにするポリシーのバージョンを展開する必要があります。|  
|**展開解除します。**|ポリシーのバージョンの展開を解除します。 バージョンがデプロイされた後、ルール ベースのアプリケーションで使用できるが不要になったです。|  
|**ポリシーのテスト**|展開する前に選択したポリシーのバージョンをテストします。|  
  
## <a name="properties-window"></a>[プロパティ] ウィンドウ  
 次の表では、ポリシーのバージョンのプロパティについて説明します。  
  
|プロパティ|値|  
|--------------|-----------|  
|**名前**|ポリシーの名前。<br /><br /> 変更することで、この値を変更することができますのみ、**名前**ポリシー (ポリシーのバージョンではなく) のプロパティ。|  
|**ファクト取得コンポーネント**|ポリシーのバージョンのファクト取得コンポーネントについて説明します。|  
|**ループの実行の最大の深さ**|実行ループの例外がスローされる前に、順行連鎖アルゴリズムの最大の深さ。<br /><br /> 既定のループ数は 65536 です。|  
|**トランザクション期間**|翻訳のタイムアウト例外の前に、ルール変換に最大時間がスローされます。<br /><br /> 既定値は、60000 ミリ秒です。|  
|**Translator**|ルールの変換に使用される変換者に関する情報。|  
|**現在のバージョン**|ポリシー エクスプ ローラーで現在選択されているポリシーのバージョン。|  
|**バージョンの説明**|現在のバージョンの説明です。|  
  
 次の表では、ルールのプロパティについて説明します。  
  
|プロパティ|値|  
|--------------|-----------|  
|**Active**|ルールを有効または無効になっているかどうかを示します|  
|**名前**|ルールの名前。|  
|**[Priority]**|ポリシー内のルールの優先度です。 値が大きい、ルールの優先順位を高くなります。 優先順位の高いルールのアクションは、最初に起動されます。<br /><br /> 既定値は 0 であり、中間の優先度を表します。|