---
title: 文字列 Values1 の処理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- jdearglist.txt, configuring strings
- strings, left-justified
- strings, configuring
- strings, right-justified
ms.assetid: a180b818-1009-45f5-a503-d10ed7dd27fc
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4a86b4b04b481e094efe703190c8da7dd86e0c14
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387605"
---
# <a name="handling-string-values"></a>文字列値の処理
このトピックでは右揃えとして特定の文字列引数を構成する方法について説明します (し、左側に埋め込み)。  
  
## <a name="types-of-string-values"></a>文字列値の型  
 JD Edwards OneWorld では、2 つの種類の相互運用性レイヤーを通じて文字列値を公開します。  
  
- char: 単一の文字  
  
- 最大文字列長  
  
  JD Edwards OneWorld では、ハンガリアン記法を使用して、ビジネス関数でこれらの型の引数の名前を付けます。 たとえば、これらの型の引数で始まります。  
  
- c  
  
- sz  
  
### <a name="left-justified-values"></a>左揃えの値  
 Sz 型の引数の大半は、最大長の文字列または文字配列、JD Edwards OneWorld には、左揃えの値が必要です。 住所行のことで、最大長が 40 は、JD Edwards OneWorld で必要があります (たとえば)。  
  
 "4567 Main St"  
  
 長さ 40 の空白で埋められます。 Microsoft BizTalk Adapter for JD Edwards OneWorld では、これを実現するための余白を入力する必要はありません。 のみ、クライアント コードで「4567 Main st.」を入力する必要があります。  
  
### <a name="right-justified-values"></a>右揃えの値  
 この種類の値のサブセットについては、JD Edwards OneWorld には、左側の余白と右揃えで配置の値が期待しています。 たとえば、B4200310 ソース モジュールでビジネス関数の場合、引数 szbusinessunit の長さは 12 です。 この引数は、生産施設などのプラントを表します。 プラント番号が 30、j. d. Edwards OneWorld XE では、値が必要です。  
  
 "          30"  
  
 右揃えになる値を入力するには、jdearglist.txt という名前のファイルにパラメーターを入力する必要があります。 スキーマを生成するときに、jdearglist.txt が読み取られます。 このテキスト ファイルに記載されている任意の値は自動的に右揃えの値に変換され、左側に空白で埋められます。  
  
 エントリをこれらのパラメーターを記述して jdearglist.txt はテキスト エディターを作成し、次のフォルダーに保存する必要があります: %BizTalk_Install_Adapter%\config\JDE\  
  
 場所 **%biztalk_install_adapter** JD Edwards OneWorld を BizTalk Adapter をインストールしたディレクトリです。  
  
 このファイルが存在しないか、空では場合、アダプターが最初に開いたときに、BizTalk Adapter for JD Edwards OneWorld のログで情報メッセージが表示されます。  
  
> [!NOTE]
>  スキーマの生成後に、このファイルを変更する場合が含まれているデータを更新するスキーマを再生成する必要があります。  
  
 このファイルの最新の情報を使用していることを確認するには、スキーマを再生成する前に、browsingagent.exe プロセスを停止するのにタスク マネージャーを使用できます。ただし、この必要はありません。  
  
 Jdearglist.txt ファイル内のエントリの形式の例を次に示します。  
  
```  
<SourceModule>.<BusinessFunction>.<Argument>  
```  
  
 例 :  
  
```  
B4200310.F4211FSBeginDoc.szBusinessUnit  
```  
  
 (同じ型) のような名前付き引数は、同じビジネス モジュールに属するビジネス関数の一連のビジネス機能の一部またはすべての間で共有されます。 ビジネス関数名ではなく、ワイルドカード文字 (*) を使用することができます。 以下に例を示します。  
  
```  
B4200310.*.szBusinessUnit  
```  
  
> [!NOTE]
>  別のコンピューターに、JD Edwards OneWorld のビジネス プロセスをインポートするときに、手動で jdearglist.txt をコピーする必要があります。  
  
## <a name="see-also"></a>参照  
 [Jdearglist での文字列の位置](../core/setting-string-justification-in-jdearglist.md)   
 [付録 a:データ型](../core/appendix-a-data-types.md)