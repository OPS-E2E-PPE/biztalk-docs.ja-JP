---
title: "エラー - XML 入力ファイルが存在しない |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: bts10.map.error.xmlInputFileDoesNotExist
ms.assetid: d222e615-60c8-46f5-a8de-fc59650978c7
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4b70e749565bcf33f99c39faa0653c7fd952e9d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error---xml-input-file-does-not-exist"></a>エラー - XML 入力ファイルが存在しません
**エラー コード**  
  
 btm1039  
  
 **説明**  
  
 マップのテスト操作用に指定されている XML 入力インスタンス メッセージ ファイルが存在しません。 ときの値、 **TestMap の入力**XML にマップのプロパティが設定されているの既存の XML インスタンス メッセージ ファイルを指定する必要があります、 **TestMap の入力インスタンス**プロパティにマップします。  
  
 **ユーザーの操作**  
  
 ソリューション エクスプ ローラーで関連するマップを右クリックし、をクリックして**プロパティ**、し、**マップのテスト** タブで、**プロパティ ページ** ダイアログ ボックス、マップをクリックして、省略記号 (**...**) の値フィールドのボタン、 **TestMap の入力インスタンス**プロパティです。 使用して、**入力ファイルの選択**ダイアログ ボックスで、既存の XML インスタンスのマップの送信元スキーマに準拠したメッセージ ファイルを選択します。 値フィールドに直接この XML ファイルのパスを入力する代わりに、 **TestMap の入力インスタンス**プロパティです。