---
title: 文字列 Values2 の処理 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- string values, configuring
- formatting strings
- strings, formatting
- left-justified string values
- jdearglist.txt
- strings, left-justified
- right-justified string values
- strings, right-justified
ms.assetid: 23d54731-b2b9-4610-a533-e041237e0bb3
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 024663faa56d92361d861a61a0d64a4608839aa6
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
ms.locfileid: "22246370"
---
# <a name="handling-string-values"></a>文字列値の処理
このトピックでは、一部の文字列引数を右揃え (および左側に埋め込み) で構成する方法について説明します。  
  
## <a name="types-of-string-values"></a>文字列値の種類  
 JD Edwards EnterpriseOne は、その相互運用性レイヤーを通じて、次の 2 種類の文字列値を公開します。  
  
-   char: 単一の文字  
  
-   最大文字列長  
  
 JD Edwards EnterpriseOne では、ハンガリアン記法を使用して、ビジネス関数でこれらの型の引数を指定します。 たとえば、これらの種類の引数は以下から始まります。  
  
-   c  
  
-   sz  
  
### <a name="left-justified-values"></a>左揃えの値  
 sz 型の引数 (最大長の文字列または文字配列) の大半について、JD Edwards EnterpriseOne では左揃えの値にする必要があります。 たとえば最大長が 40 の住所行の場合、JD Edwards EnterpriseOne では次のように指定する必要があります。  
  
 "4567 Main St.    "  
  
 長さ 40 の空白を埋めます。 空白の埋め込みは Microsoft BizTalk Adapter for JD Edwards EnterpriseOne により行われます。 クライアント コードで「4567 Main St」を入力する必要があるだけです。  
  
### <a name="right-justified-values"></a>右揃えの値  
 この種類の値のサブセットについて、JD Edwards EnterpriseOne では左側に空白が埋め込まれた右揃えの値にする必要があります。 たとえば、B4200310 ソース モジュールでのビジネス関数では、場合、引数 szBusinessUnit 長さが 12 です。 この引数は、生産施設などのプラントを表します。 プラント番号が 30 の場合、J.D. Edwards EnterpriseOne では次のように指定する必要があります。  
  
 "           30"  
  
 右揃えの値を入力するには、jdearglist.txt というファイルにパラメーターを入力する必要があります。 スキーマを生成すると、jdearglist.txt が読み取られます。 このテキスト ファイルの任意の値は右揃えの値に自動変換され、左に空白が埋め込まれます。  
  
 jdearglist.txt はテキスト エディターを使用し、これらのパラメーターを表すエントリを記述して、以下のフォルダーに保存する必要があります。  
  
 C:\Program Files\Microsoft BizTalk Adapters\JDEEnterpriseOne\config  
  
 このファイルが存在しないか空の場合、Microsoft BizTalk Adapter for JD Edwards EnterpriseOne が最初に開くときに情報メッセージがログに記録されます。  
  
> [!NOTE]
>  スキーマの生成後にこのファイルを変更した場合は、スキーマを再生成してスキーマに含まれるデータを更新する必要があります。 このファイルに含まれる最新の情報を使用していることを確認するため、スキーマを再生成する前に、タスク マネージャーを使用して browsingagent.exe プロセスを停止することができます。ただし、この確認は必須ではありません。  
  
 以下は、jdearglist.txt に記述するエントリの形式の例です。  
  
```  
<SourceModule>.<BusinessFunction>.<Argument>  
  
```  
  
 例:  
  
```  
B4200310.F4211FSBeginDoc.szBusinessUnit  
```  
  
 同じビジネス モジュールに属するビジネス関数の場合、(同じ種類の引数で) 似た名前の付いた引数は、ビジネス関数の一部またはすべてにおいて共有されます。 ビジネス関数名の代わりにワイルドカード文字 (*) を使用できます。 例:  
  
```  
B4200310.*.szBusinessUnit  
  
```  
  
> [!NOTE]
>  JD Edwards EnterpriseOne ビジネス プロセスを別のコンピューターにインポートする場合は、手動で jdearglist.txt をコピーする必要があります。  
  
## <a name="see-also"></a>参照  
 [付録 B: データ型](../core/appendix-b-data-types.md)