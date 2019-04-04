---
title: 権利の割り当て |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- user accounts, assigning permissions
- security, user accounts
- document library, new messages
- document library, unparsed
- messages, document library
- privileges
- permissions
- unparsed document library
- security, permissions
ms.assetid: cee44240-aa00-4080-9e7f-728b2421102b
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9b736fc7eb84964f9c0e74a3c319c9de1f3a3a44
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989675"
---
# <a name="assigning-rights"></a>権利の割り当てください。
前のトピックで作成された各サイト グループのドキュメント ライブラリでは、次のアクセス許可を許可する必要があります。  


|                                         ドキュメント ライブラリ                                         |                                   サイト グループ                                   | カスタム ドキュメント ライブラリのアクセス許可を適用するには |
|--------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------|----------------------------------------------|
|                                    テンプレート ドキュメント ライブラリ                                    | Payments_Creators<br /><br /> Payments_Repairers<br /><br /> Payments_Approvers |                  アイテムの表示                  |
|                                     未解析 (下記)                                     |                               Payments_Repairers                                |       表示、挿入、編集、アイテムの削除       |
|                              新しい SWIFT MT メッセージ (以下の詳細)                               |                                Payments_Creators                                |       表示、挿入、編集、アイテムの削除       |
|                              新しい SWIFT MX メッセージ (以下の詳細)                               |                                Payments_Creators                                |       表示、挿入、編集、アイテムの削除       |
|                                        Payments_Repairers                                        |                               Payments_Repairers                                |       表示、挿入、編集、アイテムの削除       |
|                                        Payments_Approvers                                        |                               Payments_Approvers                                |       表示、挿入、編集、アイテムの削除       |
| [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]_Outbox | Payments_Creators<br /><br /> Payments_Repairers<br /><br /> Payments_Approvers |       表示、挿入、編集、アイテムの削除       |

## <a name="unparsed-document-library"></a>未解析のドキュメント ライブラリ  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]メッセージ修復プロセスは、特殊な方法で解析に失敗したメッセージを処理します。 未解析メッセージ (メッセージを XML に変換することはできません) は、1 つの未解析メッセージ ドキュメント ライブラリにルーティングされます。 のみ、特定のユーザーではなく全体のグループでは、フォルダーへのアクセスを許可するのには、未解析のドキュメント ライブラリを制限する必要があります。 これにより、未解析のフォルダーが可能な限り保護が保証されます。  

 未解析メッセージの修復へのアクセス許可を持つユーザーは、MMC の構成コンソールで定義されている少なくとも 1 つの部門の修復のロールのアクセス許可を必要し、NT グループに登録する必要もあります[!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]ユーザー グループ。  

## <a name="new-swift-mt-mx-messages-document-library"></a>新しい SWIFT MT]、[MX メッセージ ドキュメント ライブラリ  
 新しい SWIFT MT メッセージと新しい SWIFT MX メッセージ ドキュメント ライブラリは、MRSR サイトのデプロイ時に作成されます。 新しい SWIFT MT メッセージと新しい SWIFT MX メッセージ ドキュメント ライブラリでは、新しい SWIFT XML テンプレートまたは「定型」のメッセージを格納します。 これらのメッセージを使用して、新しい SWIFT InfoPath XML 形式で表されるメッセージを作成することができます。 これらのメッセージは、ドキュメント ライブラリにアップロード ボタンをクリックして、ユーザーが新しい SWIFT MT メッセージと新しい SWIFT MX メッセージ ドキュメント ライブラリにアップロードされます。 さらに、指定したユーザーにアクセスを制限する SWIFT メッセージの新しいテンプレートを配布できます。 これを行うには、まず、新しいドキュメント ライブラリを作成し、ドキュメント ライブラリに必要な XML テンプレートをコピーし、.  

 FormPublish ツールの詳細については、[FormPublish ツール](http://msdn.microsoft.com/09a6ed31-5917-4776-9a5e-955af440cdac)ツール セクションでを参照してください。