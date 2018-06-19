---
title: エラー - スキーマの依存関係が有効ではありません |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- bts10.edit.error.schemaDependencyNotValid
ms.assetid: 431278f0-6cd1-4b3f-8d87-16af4991d354
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36326608f191b520c41cb42890aec029c432fd30
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241394"
---
# <a name="error---schema-dependency-not-valid"></a>エラー - スキーマの依存関係が有効ではありません。
**エラー コード**  
  
 BEC2009  
  
 **説明**  
  
 すべての依存スキーマ (現在のスキーマにインポート、包含、再定義された依存スキーマなど) は、この BizTalk プロジェクトに追加するか、このプロジェクトによって参照されるアセンブリ内に存在する必要があります。 偶数スキーマ**インポート**、**を含める**、および**を再定義**リモート Web サイト上で指定するディレクティブは、この BizTalk プロジェクトに追加する必要があります。  
  
 **ユーザーの操作**  
  
 使用して、**既存項目の追加**コマンドを**ファイル**メニューと BizTalk プロジェクトにこのスキーマが依存しているすべてのスキーマを追加する Microsoft® BizTalk® Server プロジェクトのショートカット メニュー。 BizTalk プロジェクトにスキーマを追加する前に、スキーマを Web サイトからローカル ハード ディスクにダウンロードする必要が生じる場合もあります。