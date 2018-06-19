---
title: エラー - ネイティブの入力ファイルが存在しない |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.map.error.nativeInputFileDoesNotExist
ms.assetid: 17713896-8557-4bf1-b5f0-871b905ae15e
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 333849007c808a20130f10dfb1f22a756024a4c2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241890"
---
# <a name="error---native-input-file-does-not-exist"></a>エラー - ネイティブの入力ファイルが存在しません
**エラー コード**  
  
 btm1040  
  
 **説明**  
  
 マップのテスト操作で使用するように指定されたネイティブ入力インスタンス メッセージ ファイルが存在しません。 ときの値、 **TestMap の入力**マップのプロパティに設定されている**ネイティブ**、既存のネイティブ インスタンス メッセージ ファイルを指定する必要があります、 **TestMap の入力インスタンス**マッププロパティ。  
  
 **ユーザーの操作**  
  
 ソリューション エクスプ ローラーで関連するマップを右クリックし、をクリックして**プロパティ**、し、**マップのテスト** タブで、**プロパティ ページ** ダイアログ ボックス、マップをクリックして、省略記号 (**...**) の値フィールドのボタン、 **TestMap の入力インスタンス**プロパティです。 **入力ファイルの選択**ダイアログ ボックスで、既存のネイティブ インスタンス マップの送信元スキーマに準拠したメッセージ ファイルを選択します。 値フィールドに直接このネイティブ ファイルのパスを入力する代わりに、 **TestMap の入力インスタンス**プロパティです。