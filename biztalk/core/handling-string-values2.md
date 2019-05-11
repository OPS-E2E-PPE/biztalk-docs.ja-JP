---
title: 文字列 Values2 の処理 |Microsoft Docs
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
ms.openlocfilehash: 54d6e6ca9af087139b48465624a681aa5e6125d1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344363"
---
# <a name="handling-string-values"></a>文字列値の処理
このトピックでは右揃えとして特定の文字列引数を構成する方法について説明します (し、左側に埋め込み)。  
  
## <a name="types-of-string-values"></a>文字列値の型  
 JD Edwards EnterpriseOne では、2 つの種類の相互運用性レイヤーを通じて文字列値を公開します。  
  
- char: 単一の文字  
  
- 最大文字列長  
  
  JD Edwards EnterpriseOne では、ハンガリアン記法を使用して、ビジネス関数でこれらの型の引数の名前を付けます。 たとえば、これらの型の引数で始まります。  
  
- c  
  
- sz  
  
### <a name="left-justified-values"></a>左揃えの値  
 Sz 型の引数の大半は、最大長の文字列または文字配列、JD Edwards EnterpriseOne には、左揃えの値が必要です。 例については、住所行の場合これはの最大長が 40、JD Edwards EnterpriseOne は (たとえば) が必要です。  
  
 "4567 Main St"  
  
 長さ 40 の空白で埋められます。 Microsoft BizTalk Adapter for JD Edwards EnterpriseOne では、これを実現するための余白を入力する必要はありません。 のみ、クライアント コードで"4567 Main St"を入力する必要があります。  
  
### <a name="right-justified-values"></a>右揃えの値  
 この種類の値のサブセットについては、JD Edwards EnterpriseOne には、左側の余白と右揃えで配置の値が期待しています。 たとえば、B4200310 ソース モジュールでビジネス関数の場合、引数 szbusinessunit の長さは 12 です。 この引数は、生産施設などのプラントを表します。 プラント番号が 30、JD Edwards EnterpriseOne には、値が必要です。  
  
 "           30"  
  
 右揃えになる値を入力するには、jdearglist.txt という名前のファイルにパラメーターを入力する必要があります。 スキーマを生成するときに、jdearglist.txt が読み取られます。 このテキスト ファイル内の値は自動的に右揃えの値に変換され、左側に空白で埋められます。  
  
 エントリをこれらのパラメーターを記述して jdearglist.txt はテキスト エディターを作成し、次のフォルダーに保存する必要があります。  
  
 C:\Program Files\Microsoft BizTalk Adapters\JDEEnterpriseOne\config  
  
 このファイルが存在しないか、空では場合、情報メッセージが表示されます BizTalk adapter JD Edwards EnterpriseOne のログのアダプターが最初に開いたとき。  
  
> [!NOTE]
>  スキーマの生成後に、このファイルを変更する場合が含まれているデータを更新するスキーマを再生成する必要があります。 このファイルの最新の情報を使用していることを確認するには、スキーマを再生成する前に、browsingagent.exe プロセスを停止するのにタスク マネージャーを使用できます。ただし、この必要はありません。  
  
 Jdearglist.txt ファイル内のエントリの形式の例を次に示します。  
  
```  
<SourceModule>.<BusinessFunction>.<Argument>  
  
```  
  
 例 :  
  
```  
B4200310.F4211FSBeginDoc.szBusinessUnit  
```  
  
 (同じ型) のような名前付き引数は、同じビジネス モジュールに属するビジネス関数の一連のビジネス機能の一部またはすべての間で共有されます。 ビジネス関数名ではなく、ワイルドカード文字 (*) を使用することができます。 例 :  
  
```  
B4200310.*.szBusinessUnit  
  
```  
  
> [!NOTE]
>  別のコンピューターに、JD Edwards EnterpriseOne のビジネス プロセスをインポートするときに、手動で jdearglist.txt をコピーする必要があります。  
  
## <a name="see-also"></a>参照  
 [付録 b:データ型](../core/appendix-b-data-types.md)