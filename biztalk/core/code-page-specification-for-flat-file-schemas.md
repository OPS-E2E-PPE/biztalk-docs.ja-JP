---
title: コード ページ指定フラット ファイル スキーマの |Microsoft Docs
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
ms.openlocfilehash: 5b0ba2c19c3fc02ff0a72fcd8e93ec9f4b112996
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357174"
---
# <a name="code-page-specification-for-flat-file-schemas"></a>フラット ファイル スキーマのコード ページの仕様

## <a name="overview"></a>概要
値、**コード ページ**逆アセンブリおよびフラット ファイル ドキュメントのアセンブリの中で使用されるエンコード オブジェクトを作成するプロパティを使用します。 このエンコーディング オブジェクトにより、Microsoft によって内部的に使用される正規化された utf-8 エンコードに、受信フラット ファイル ドキュメントのネイティブ エンコードに変換するフラット ファイル パーサー[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]します。 エンコーディング オブジェクトでは、内部の utf-8 エンコードでは、フラット ファイル ドキュメントのネイティブ エンコードに変換するフラット ファイル シリアライザーもできます。  
  
 設定、**コード ページ**プロパティが、フラット ファイル ビジネス ドキュメントで使用される文字エンコード体系を決定する際、排他的ではないが、重要な役割を果たします。 メッセージは、送信メッセージがフラット ファイル形式に変換された、フラット ファイル アセンブラーの文字はエンコードする方法とフラット ファイル逆アセンブラーによって解釈されます。 フラット ファイルを受信する方法を検討する必要があります。  

## <a name="character-encoding"></a>文字エン コード  
 指定されたインスタンス メッセージの文字エン コードの処理方法を次のように決定する役割を果たす複数の要因があります。  
  
-   フラット ファイル インスタンス メッセージを逆アセンブルするとき、次のアルゴリズムを使用して確認し、エンコード情報を保持を。  
  
    1.  場合、 **Charset**メッセージのボディ部では、設定された場合、その値を使用します。  
  
    2.  それ以外の場合、エンベロープ (またはドキュメント) スキーマを使用してコード ページを指定する場合、**コード ページ**プロパティ、その値を使用します。  
  
    3.  それ以外の場合、バイト順マークが存在する場合は、その値が使用されます。  
  
    4.  それ以外の場合、utf-8 を想定しています。  
  
-   フラット ファイル インスタンス メッセージをアセンブルするときに、次のアルゴリズムを使用してデコードで使用する文字セットの決定を。  
  
-   場合、 **XMLNorm.TargetCharset**メッセージ コンテキスト プロパティの設定、その値が使用されます。  
  
-   の場合、 **TargetCharset**アセンブラー (デザイン時) プロパティが設定されて、その値が使用されます。  
  
-   それ以外の場合、エンベロープ (またはドキュメント) スキーマを使用してコード ページを指定する場合、**コード ページ**プロパティ、その値を使用します。  
  
    1.  の場合、 **SourceCharset**メッセージ コンテキスト プロパティの設定、その値が使用されます。  
  
    2.  それ以外の場合、utf-8 を使用します。  
  
## <a name="see-also"></a>参照  
 **ファイル メッセージ スキーマをフラットを作成する際の考慮事項**と**コード ページ (フラット ファイル スキーマのノード プロパティ)** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]