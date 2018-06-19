---
title: コード ページ指定フラット ファイル スキーマの |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 825e75f1-893c-4c61-b566-f893d732a907
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64d5cfbc960346e702ed0d4a39ca74bbc4b3634c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232266"
---
# <a name="code-page-specification-for-flat-file-schemas"></a>フラット ファイル スキーマのコード ページ仕様

## <a name="overview"></a>概要
値、**コード ページ**逆アセンブリおよびフラット ファイル ドキュメントのアセンブリの中で使用されるエンコード オブジェクトを作成するプロパティを使用します。 このエンコード オブジェクトを使用すると、フラット ファイル パーサーでは、受信フラット ファイル ドキュメントのネイティブ エンコードを、Microsoft [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] によって内部的に使用される正規化された UTF-8 エンコードに変換できます。 また、フラット ファイル シリアライザーでは、内部の UTF-8 エンコードをフラット ファイル ドキュメントのネイティブ エンコードに戻すことができます。  
  
 設定、**コード ページ**プロパティは、フラット ファイル ビジネス ドキュメントで使用される文字エンコード体系を決定するとき、排他的ではないが、重要な役割を果たします。 送信メッセージがフラット ファイル形式に変換される場合、フラット ファイル アセンブラーが文字をエンコードする方法とフラット ファイル逆アセンブラーが受信フラット ファイル メッセージを解釈する方法を考慮する必要があります。  

## <a name="character-encoding"></a>文字エン コード  
 次のように、特定のインスタンス メッセージの文字エンコードを処理する方法を決める複数の要因があります。  
  
-   フラット ファイル インスタンス メッセージを逆アセンブルする場合、次のアルゴリズムを使用して、エンコード情報の決定および保存が行われます。  
  
    1.  場合、 **Charset**メッセージのボディ部では設定された場合、その値を使用します。  
  
    2.  それ以外の場合、エンベロープ (またはドキュメント) スキーマでは、コード ページを使用して、指定する場合、**コード ページ**プロパティ、その値を使用します。  
  
    3.  上記に該当しない場合、バイト順マークが存在すると、その値が使用されます。  
  
    4.  上記に該当しない場合、UTF-8 を使用します。  
  
-   フラット ファイル インスタンス メッセージをアセンブルする場合、次のアルゴリズムを使用して、デコードで使用する文字セットが決まります。  
  
-   場合、 **XMLNorm.TargetCharset**メッセージ コンテキスト プロパティが設定されて、その値を使用します。  
  
-   それ以外の場合、 **TargetCharset**アセンブラー (デザイン時) プロパティが設定されて、その値を使用します。  
  
-   それ以外の場合、エンベロープ (またはドキュメント) スキーマでは、コード ページを使用して、指定する場合、**コード ページ**プロパティ、その値を使用します。  
  
    1.  それ以外の場合、 **SourceCharset**メッセージ コンテキスト プロパティが設定されて、その値を使用します。  
  
    2.  それ以外の場合、utf-8 を使用します。  
  
## <a name="see-also"></a>参照  
 **ファイル メッセージ スキーマをフラットを作成する際の考慮事項**と**コード ページ (フラット ファイル スキーマのノード プロパティ)**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]